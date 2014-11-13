# A Cleverly Named Library

---

The idea behind this code is to extract out commonalities from the computational philosophy workshop and wrap them up into a library that can be published on github and elsewhere.

Currently, code for each workshop has been broken down into a simulation module detailing the agent behaviour and a browser module that uses D3.js for rendering behaviour in the browser.  These modules need to be compiled with browserify and coffeeify for any change made to them.

My new idea is to have all the variables that will change in the simulation coded into the HTML index page, or better yet, added via query strings to enable dynamic links.  Let's try it out....

---


First up, lets define the entities in our simulation.  We'll start with two - agents and the space they exist in.  A space is a 2D representation of the problem domain.  We instantiate a space with some x,y constraints and an agent profile.


		class Space
			constructor: (@height, @width, agent_profile) ->
				@populate agent_profile


We populate our space from an agent profile.  This profile contains an array such as `[0, 250, 250]` which tells our space to create 250 agents each based on the the 2nd and 3rd strategies profiles defined earlier.


		Space::populate = (agent_profile) ->
			@agents = []
			type = 0
			for type, num of agent_profile
				for n in [0..num]
					@agents.push new Agent this, if type is 'red' then 0.33 else 0.66


So who are these agents?  These simple fellas exist in a space and hold a credence for a particular belief.  We also give them a step length in case they will be walking, and a state machine to see if they have spoken.


		class Agent
			constructor: (@space, @credence=0.5) ->
				@step = 3
				@spoken = null


Agents can be arranged in a space either deterministically or stochastically, and this arrangement can relate to either where they are (what x,y coordintate an agent occupies) or what they are (what type of agent is in that x,y coordintate).  The cluster method accepts 2 arguments between `0.0` and `1.0` relating the degree of determinism concerning where an agent is located and what the agent is.

The what-algorithm is a modified Fisher-Yates shuffle that is applied stochastically if the what-cluster value is exceded.  The where-algorithm orders agents in straight lines or stochastically if the where-cluster is exceded.


		Space::cluster = (where, what) ->
			#what
			for i in [@agents.length-1..1]
				unless what > Math.random()
					j = Math.floor Math.random() * (i + 1)
					[@agents[i], @agents[j]] = [@agents[j], @agents[i]]

			# where
			block = Math.sqrt @width * @height / @agents.length
			x = y = block / 2
			for agent, position in @agents
				hurdle = Math.random()
				agent.x = if where > hurdle then x else Math.floor Math.random() * @width
				agent.y = if where > hurdle then y else Math.floor Math.random() * @height
				x += block if x < @width
				if x > @width 
					y += block
					x = block / 2
			@agents


In spacial arranements, everybody is next to somebody - their neighbour.  A neighbourhood is simply a list of all the agents within an agent's depth perception.  Here we return everyone within a square from an x, y coordinate.


		Space::neighbourhood = (x, y) ->
			@depth = Math.sqrt(@width * @height / @agents.length) + 1
			neighbours = []
			for other in @agents
				if x - other.space.depth < other.x < x + other.space.depth and y - other.space.depth < other.y < y + other.space.depth
					neighbours.push other
			neighbours


In every tick of the simulation, agents will interact with others in their neighbourhood and update their credences based on the credences of their neighbours.  Currently, we don't need to use the interact method so we'll use it to simply invoke the adapt behaviour.

	
		Agent::adapt = () ->
			neighbours = @space.neighbourhood(@x, @y)
			blue_count = 0
			red_count = 0
			for neighbour in neighbours
				blue_count = if neighbour.credence > 0.5 then 1 else 0
				red_count = if neighbour.credence > 0.5 then 0 else 1

			numerator = Math.pow(1-@credence, red_count) * @credence
			denominator = Math.pow(1-@credence, red_count) * @credence +
											Math.pow(@credence, blue_count) * (1-@credence)
			@credence = numerator / denominator

			@credence = 1.0 if @credence > 1.0
			@credence = 0.0 if @credence < 0.0
			@credence

			
Communicating beliefs


		Agent::communicate = () ->
			@spoken = if @credence > 0.5 then 'blue' else 'red'



Let's also throw in some logic for walking our agents around the space.  Movement could be intentionally directed or (as in this case), agents move to a random spot near by.


		walk = (agent) ->
			xRand = Math.random() * agent.step
			yRand = Math.random() * agent.step
			agent.x += xRand - agent.step / 2
			agent.x = xRand / 2 if agent.x < 0
			agent.x = agent.space.width - xRand /2 if agent.x > agent.space.width
			agent.y += yRand - agent.step / 2
			agent.y = yRand /2 if agent.y < 0
			agent.y = agent.space.height - yRand / 2 if agent.y > agent.space.height
			agent


Now that we have defined our model, we need some functions to initiate and control behaviour.  We will instantiate the simulation by invoking the agents function.  This will create a space and populate it with agents according to our profile.  We will set the cluster values so that agents are perfectly ordered in space but randomly allocated to a space.  Try adjusting the facts to see what happens! 


		agents = (height, width) ->
			space = new Space height, width, {red: 1000, blue: 1000}
			space.cluster 1.0, 0.5


		reset = (agent) ->
			agent.spoken = null 

		talk = (agent) ->
			agent.adapt()
			walk agent
			agent

		adapt = () ->

		space = () -> 
			new Space()

		agent = () ->
			new Agent()


Finally, we declare our public API so that other modules can access it.

		
		simulation = {create: agents, interact: talk, adapt: adapt, reset: reset, space: space, agent: agent}
		module.exports = simulation


That's it. The simulation complete.