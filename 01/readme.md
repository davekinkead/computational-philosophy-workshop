### Computational Philosophy Workshop


# Introduction & Setup

Welcome to the first session of the computational philosophy workshop!  The purpose of this workshop is to provide an informal (and non-assessed) environment in which we can actively explore how computational methods can be used as a method of philosophical enquiry.

We will be learning by doing.  We will be using agent based modelling to explore and examine some of the claims made in the cannons of political thought - such as The Leviathan, The Social Control, the Second Treatise of Government.  There will be some programming involved but the focus will be on clarifying and formalising the claims made by Hobbes, Rousseau, and Locke.

This is a hands on workshop - you don't need to know how to program but you will need to actively participate in discussions (and you will need your own computer).  You'll also need to help others - if you are into IT, then please help those struggling with their interwebs.  If you know your Hobbes and Rousseau, even better - you can help those who haven't read much political philosophy before.  Be nice, ask questions, have fun.

The plan for this session is as follows:

- welcome
- workshop objectives
- simulation in philosophy
- agent based modelling
- co-authoring our paper


## Simulation & Philosophy

Models have been a part of philosophy since the pre-Socratic days. When Thales proposed his cosmological thesis, he was using a model of the world that claimed that water was the essence of nature.

Models are theories.  They abstract matters irrelevant and simplify by focusing only on the relata we need for understanding.

Models are both descriptive and predictive.  Their descriptive use allows us to tell stories about how the world works, and aid our understanding of things.  Their predictive use gives them value as tools, and also acts a metric of their accuracy.

Logic, for example, is a model of reason.  In propositional logic, we abstract away the content of propositions and because we are only concerned with the relationships between propositions.

    A -> B
    ~B
    ---
    ~A

Computational models then are just the formalisation in code of theoretical models.

### Do computer models bring anything unique to philosophy?

While modelling in philosophy is nothing new or radical, the use of computational methods certain is.  Claims of novelty regarding computational methods are typically thought to be based around these broad areas: (@friggs2009 p595)

- Metaphysical: Simulations create some kind of parallel world in which experiments can be conducted under more favourable conditions than in the ‘real world’.   
- Epistemic: Simulations demand a new epistemology.  
- Semantic: Simulations demand a new analysis of how models/theories relate to con- crete phenomena.  
- Methodological: Simulating is a Sui Generis activity that lies ‘in between’ theorising and experimentation.  

Friggs & Riess come to the conclusion that while computer simulations certain offer something new to science, they don't create anything new for the philosophy of science.  But how well does that argument hold up?

Knowledge can be broadly classified as rational or empiric.  Simulations however, contribute to what could be called generative knowledge - knowledge that is based derived from empiric like data but concerns only assumption rather than the external world.

A good example of this is emergence is flocking behaviour - see [video](http://www.youtube.com/watch?v=8vhE8ScWe7w&t=33s)

Something that is certainly new in social philosophy is using simulations as coherence tests.  The idea, and the focus of these workshops, is to model the assumptions made by various political theories and simulate them to see if their claimed outcomes and conclusions really do occur.

This is certainly something new to philosophy, and something that is only possible with the computational power of modern computers.

Examples

- [ants](http://agentscript.org/models/ants.html)
- [flocks](http://agentscript.org/models/flock.html)

## Agent Based Modelling

Agent-based models typically have three elements:

1. A set of agents, their attributes and behaviours.
2. A set of agent relationships and methods of interaction: An underlying topology of connectedness defines how and with whom agents interact.
3. The agents’ environment: Agents interact with their environment in addition to other agents.

Within models, agents have the following essential characteristics:

1. Agent are self-contained, modular, and uniquely identifiable individuals.
2. Agent are autonomous and self-directed.
3. Agents have state that varies over time. 
4. Agents interact dynamically with their environment. 

Agents may also have other useful characteristics:

1. Agents may be adaptive.
2. Agent may be goal-directed (strongly linked to autonomy)
3. Agents may be heterogeneous.

-- [Macal & North 2010](http://www.palgrave-journals.com/jos/journal/v4/n3/full/jos20103a.html for more details)




## Readings

Please ensure you've done the readings before the workshop as I want to spend as much quality time as possible discussing, analysing, and building stuff.

1. Frigg, R. and Reiss, J. (2009). [_The philosophy of simulation: hot new issues or same old stew?_][j1]. Synthese, 169(3), pp.593--613. 
2. Railsback, S. and Grimm, V. (2011). [_Agent-based and individual-based modeling: a practical introduction._][b1]  Chapter 1 _Models, Agent-Based Models, and the Modelling Cycle_

[j1]: https://www-jstor-org.ezproxy.library.uq.edu.au/stable/40271311
[b1]: http://goo.gl/1zQ1LQ


## Setting up your computer

Try and set up your system before the first workshop so we can spend that time working through any installation problems.  We'll be using the following free and/or open-source software during the semester...


### Git

> Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.   
> -- [git-scm.com](http://git-scm.com)

Version control is important for writing philosophy but it is even more important for writing code.  The simplest way to conceptualise git is with the idea of snap shots.  A git `commit` is a snap shot of a project directory at a given moment.  You can jump between commits at any time to view your work as it was at the time of the commit.

Commits link together temporally to form `branches`.  A new branch can be forked from any commit allowing you to work on conceptually distinct features.  Imagine your workflow like a tree with ideas forking from the `master` branch.

If you are happy with your work on a particular branch, you can `merge` it with your master (or any other) branch.  If not, you can discard it and jump back to another branch.  You can jump between branches any time you like allowing you to work on conceptually distinct features simultaneously.

There are plenty of good git tutorials online [here](https://try.github.io), [here](http://git-scm.com/book), and [here](http://pcottle.github.io/learnGitBranching/)


### Github

> GitHub is the best place to share code with friends, co-workers, classmates, and complete strangers.  
> -- [github.com](https://github.com)


Github is an online extension to git.  It provides hosting for git repos and has lots of features that make collaborative work easier.  

1. Sign up for an account (use an edu email for free private repos)
2. [Fork](https://github.com/davekinkead/computational-philosophy-workshop/fork) & [watch](https://github.com/davekinkead/computational-philosophy-workshop/subscription) the [computational-philosophy-workshop](https://github.com/davekinkead/computational-philosophy-workshop) repo.  You'll then get email notifications whenever content gets updated.
3. Learn how to ask a question in a distributed environment by [creating an issue](https://github.com/davekinkead/computational-philosophy-workshop/issues/new).


### Node

> Node.js is a platform built on Chrome's JavaScript runtime for easily building fast, scalable network applications. Node.js uses an event-driven, non-blocking I/O model that makes it lightweight and efficient, perfect for data-intensive real-time applications that run across distributed devices.  
>  -- [NodeJS](http://nodejs.org/)

Node is an asynchronous server side environment for running Javascript, and that is all you need to know about it.  Install node on your system by following [these instructions](http://nodejs.org/download/).


### Coffeescript

> CoffeeScript is a little language that compiles into JavaScript.   
> -- [Coffeescript.org](http://coffeescript.org/)

We'll be writing our simulation code in coffeescript for a number of reasons:

1. It has an expressive syntax that is similar to natural language English;
2. It compiles to javascript so it works both on a server and in the browser; and
3. Most importantly, I like it & I am hosting the workshop!

To install Coffeescript, you first need to install NodeJS (above), then open up your terminal and type:

    npm install -g coffee-script
