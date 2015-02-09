### Computational Philosophy Workshop

# Models of Segregation

This week we are going to being building some simple agent based models based on a classic paper from sociology - Thomas Schelling's [Models of Segregation][mos]

## Recap of Week One

[Last week](01-introduction.md) we briefly covered some concepts of agent based simulation and some of the related philosophical notions that accompany this type of work.  The type of simulations we will be doing in these workshops could best be described as coherence test - simulations of political theory to test the coherence between assumptions, premises, and conclusions.

We also setup our systems (or at least attempted to for Windows users) for actually building models.  We installed git, NodeJS, and coffee script, and signed up to github.  

To check everything is working, open your terminal (command line) and type (or copy each line):


		coffee
		life = "solitary, poor, nasty, brutish and short"
		spawn = require('child_process').spawn
		spawn "open", ["http://www.youtube.com/watch?v=pATX-lV0VFk&t=40s"] if life is life
      

If you are on windows and that last line didn't work, try 


    spawn "explorer.exe", ["http://www.youtube.com/watch?v=pATX-lV0VFk&t=40s"] if life is life


## Models of Segregation

Thomas Schelling's Models of Segregation is an important work of mathematical sociology thanks to it's use of simple mathematical models to debunk a widely held belief, namely that highly segregated societies are the result of systematic racism.

Shelling's paper shows that rather than being the exclusive result of racism, segregation can occur due to "the interplay of individual choices ... with collective results that bear no close relation to individual intent." (@shelling1969 p488)

Rather than a system based model approach that Schelling used, we will be using agent based modelling to explore how individual agent preferences can result in emergent system level behaviour.

I've created a new repo for this simulation [over here](https://github.com/davekinkead/models-of-segregation) with detailed explainations in the code.


## Readings

Schelling, Thomas (1969) [Models of Segregation][mos], _The American Economic Review_
Vol. 59, No. 2, Papers and Proceedings of the Eighty-first Annual Meeting of the American Economic Association, pp. 488-493


[mos]: http://www.jstor.org/stable/1823701