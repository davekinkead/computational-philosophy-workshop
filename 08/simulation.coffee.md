

So lets our model with the problem space...


		class Space


The space will be populated by agents who hold a belief or credence concerning some matter with a value ranging from 0.0 to 1.0 and a default value of 0.5.


		class Agent
			constructor: (@belief=0.5) ->




		console.log new Agent(.2)


