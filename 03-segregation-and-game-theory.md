### Computational Philosophy Workshop

# Simulation, Segregation, and Game Theory

Last workshop, we created an agent based simulation of segregation effects based on Thomas Schelling's 1969 work.

This week, we are going to add some more complexity to our models by incorporating game theory.  The workshop will largely be a reproduction of [this paper][grim] by Patrick Grimn so you'll need to read that and brush up on [some basic][wiki] [game theory][sep].

## Game Theory

Game theory is the mathematical study of interactive decision making.  Fully defined games specify:

1. players
2. information
3. actions
4. payoffs

We can represent games in extensive (tree) or normal (strategic) form.  Here, we'll use normal form simply because of formating ease.  Normal form looks like a matrix listing player payoffs (2 player game below)


		4, 3	| 	2, 1
		------------------
		-1,-3	|	10,-5


### Types of Games

There are many different classifications of game - cooperative & non-cooperative, symmetrical & asymmetrical, zero sum & non-zero sum.

When players are able to form binding commitments a game is cooperative. When they cannot, the game is non-cooperative.

When payoffs in a game depend only on the strategy employed but not who employs the strategy, the game is symmetric.  When this is not the case and players have access to different strategies, the game is asymmetric. 

When the total payoffs of every strategy combination sum to zero, the game is a zero sum game.	Non-zero sum games are when payoffs don't.

Two important games we are going to focus on in this series are the prisoner's dilemma and the stag hunt.

The prisoner's dilemma is a non-zero sum, non-cooperative, symmetric game.  It occurs when the payoffs are maximised for cooperative behaviour but when individual self-maximising leads to negative sum outcomes.  The game in normal form looks like this:


		2, 2	| 	0, 3
		------------------
		3, 0	|	1, 1


In the prisoner's dilemma, the relationship between payoffs means that even though cooperation has the best mutual payoff (2, 2), players will always defect (1, 1) because regardless of what the other player does, defection maximises individual payoff (3 beats 2 and 1 beat 0 - a Nash equilibrium).

In iterative games, tit-for-tat (or just do what the other player did last round), is the most successful deterministic strategy to employ.  Interestingly, tit-for-tat never wins in any single round, but outperforms by losing the least.

In Robert Axelrod's [The Evolution of Cooperation](http://en.wikipedia.org/wiki/The_Evolution_of_Cooperation), he showed that the most successful strategies were:

- nice: they didn't defect first
- retaliating: they need to punish defectors
- forgiving: they must break defection cycles
- non-envious: they must not attempt to beat an opponent

The stag hunt differs from the prisoner's dilemma in that the payoffs for mutual defection are different.  In this case, there are 2 Nash Equilibria - 2,2 and 1,1.  In the stag hunt, players gain most from mutual cooperation, gain some from mutual defection, but lose most if they are suckered. 

	
		2, 2	| 	0, 1
		------------------
		1, 0	|	1, 1


On other game that might be relevant is the snow drift.  here, players gain some from mutual cooperation, some from being suckered and most from suckering, but least from mutual defection - a classic free rider scenario.


		2, 2	| 	1, 3
		------------------
		3, 1	|	0, 0

## Workshop

In this weeks workshop, we are going to reproduce part of the paper below.  After modeling segregation last week, we will produce an agent based model of the [spatialised prisoner's dilemma](http://dave.kinkead.com.au/spatialised-prisoners-dilemma/).


### Readings

Grim, Patrick, et al. ["Reducing prejudice: A spatialized game-theoretic model for the contact hypothesis."][grim] Artificial life IX (2004): 244-249.



[grim]: http://stanford.edu/~wbraynen/papers/ALife2004.pdf

[wiki]: http://en.wikipedia.org/wiki/Game_theory

[sep]: http://plato.stanford.edu/entries/game-theory/