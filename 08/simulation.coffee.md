# Information Cascades

## Simulation Code


First up, lets define the entity in our simulation.  We'll start with two - agents and the space they exist in.  Agents exist in a space hold a game strategy which is assigned randomly if none is provided.  We also give them a step length in case they will be walking.


		class Agent
			constructor: (@space, @strategy) ->
				@step = 5
				@colour = 'blue'


Agents live in a space which we define as a 2D space representing the problem domain.  When we crate a space, we populate it with agents, and give it a neighbourhood depth value.


		class Space
			constructor: (@height, @width, agent_profile) ->
				@populate agent_profile


We populate our space from an agent profile.  This profile contains an array such as `[0, 250, 250]` which tells our space to create 250 agents each based on the the 2nd and 3rd strategies profiles defined earlier.


		Space::populate = (agent_profile) ->
			@agents = []
			type = 0
			for i,v in agent_profile
				for n in [0..i]
					@agents.push new Agent this, 'play nice'


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

This could in future be extended to allow von Newman neighbourhoods, and Moore neighbourhoods


		Space::neighbourhood = (x, y) ->
			@depth = Math.sqrt(@width * @height / @agents.length) + 1
			neighbours = []
			for other in @agents
				if x - other.space.depth < other.x < x + other.space.depth and y - other.space.depth < other.y < y + other.space.depth
					neighbours.push other
			neighbours



Next, lets define some strategies a player could employ in any 2 player game.  These are specified by their inital move `i`, responding to cooperation move `c`, and responding to defection move `d`.  We'll also name these and give them pretty colours and store them in a list.


Now we turn to our game.  The browser will trigger the main game interface `interact(agent)` every tick.  Each agent finds their neighbours and plays against them for a number or rounds, with the agent score calcuated from the payoff matrix.  In every contest, we set the agent score and last_game values to 0.  We also throw in some Brownian motion to encourage disequilibrium.


		interact = (agent) ->
			walk agent
			agent
			


We also need to define the interaction between agents.  The initial move is dictated by the agent's strategy while subsequent moves are based on an opponents last move.



Agents also need to update their strategy after each round.  We will do this only after all contests in a tick have finished and scores have been calculated.  If the agent score is the equal highest score, then no change to strategy will be made.


		update = (agent) ->

			agent


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


Now that we have defined our model, we need some functions to initiate and control behaviour.  We will instantiate the simulation by invoking the `agents` function.  This will create a space and populate it with agents according to our profile.  We will set the cluster values so that agents are perfectly ordered in space but randomly allocated to a space.  Try adjusting the facts to see what happens! 


		agents = (height, width) ->
			space = new Space height, width, [1985, 10, 5, 25]
			space.cluster 1.0, 0.0


Finally, we declare our public API so that other modules can access it.

		
		module.exports = {create: agents, interact: interact, update: update}

That's it. The simulation complete.