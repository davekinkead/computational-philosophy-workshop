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

## Readings

Please ensure you've done the readings before the workshop as I want to spend as much quality time as possible discussing, analysing, and building stuff.

1. Roman Frigg and Julian Reiss, [_The philosophy of simulation: hot new issues or same old stew?_](https://www-jstor-org.ezproxy.library.uq.edu.au/stable/40271311) Synthese Vol. 169, No. 3 (Aug 2009) pp. 593-613
2. Models, Agent-Based Models, and the Modelling Cycle.


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
