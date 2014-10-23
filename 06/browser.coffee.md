# Browser Code

This is the browser file where we pull together different parts of the simulation and wrap it up in the browser.  We'll start out by importing our libraries and defining any global variables we might need.


		d3 = require './assets/d3.min.js'
		simulation = require './simulation.coffee.md'
		running = true
		height = window.innerHeight || 600
		width = window.innerWidth || 600
		space = null

		game = window.location.search.match /\?game=(.+)&?/


Next, we'll grab create our svg canvas, apply some event listeners and add it to the DOM.


		canvas = d3.select("#space")
					.append("svg:svg")
					.attr("height", height)
					.attr("width", width)
					.on "click", () ->
						running = false
						alert 'Simulation stopped'

		info = d3.select("#info")
					.on "click", () ->
						d3.select("#info p").style "display", "none"
						d3.select("#info h1").style "font-size", "1em"

Now we need to createsvg circles to represent our agents and bind them to the actual agents from the simulation.  The `d` in the functions here is the D3js accessor to the agent data.

	
		populate = () ->
			space = simulation.agents(height, width)
			canvas.selectAll "circle"
				.data space
				.enter().append "circle"
				.style "fill", (d) -> d.strategy.color 
				.style "opacity", 0.5
				.attr "r", 8
				.attr "cx", (d) -> d.x
				.attr "cy", (d) -> d.y

		populate()


We then write a loop where each svg circle triggers the move function for its bound agent.  


		move = () ->
			circles = canvas.selectAll "circle"
			circles.each (d) ->
				d = simulation.interact d
			.each (d) ->
				d = simulation.update d
			.transition()
			.duration 500
			.attr "cx", (d) -> d.x
			.attr "cy", (d) -> d.y
			.attr "r", (d) -> 
				if d.strategy.i is 3 then 10 else Math.max 3, (d.score / 10)
			.attr "title", (d) -> "#{d.strategy.name} - #{d.score}"
			.style "fill", (d) -> d.strategy.color
		

		run = () ->
			move() unless running is false


Finally, we run the loop continuous with a half second pause.


		setInterval run, 500