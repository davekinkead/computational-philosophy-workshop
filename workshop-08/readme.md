### Computational Philosophy Workshop #8

# Information Cascades

Information cascades can occur when agents can see what others do but not what they know, and need to make choices sequentially.  As [Ivo Welch](http://info-cascades.ivo-welch.info/) defines it:

> An information cascade is a situation in which every subsequent actor, based on the observations of others, makes the same choice independent of his/her private signal.

[Background Reading](http://www.cs.cornell.edu/home/kleinber/networks-book/networks-book-ch16.pdf)

So consider the following hypothetical:

> Alice, Bob, & Charlie are independently trying to decide where to dine on their first night out in a new city.  They have a choice between two restaurants - Thai or Indian - and like both cuisines equally.  They do know that one is definitely better than the other because they read some reviews but unfortunately only know with some certainty (66%) which one that is.  Alice chooses first, then Bob then Charlie.  Later diners see earlier ones choose and they all know that each has the same credence for the correct choice.

Alice thinks Thai is better so chooses that one. If Bob thinks Thai is better, then he should obviously choose Thai as well but if he privately thinks Indian is the better choice then he has a dilemma. He knows that Alice chose Thai which is evidence that Alice privately thought Thai was better.  He now has conflicting evidence - effectively one vote for each restaurant - which reduces his credence from 66% to 50%.  From Bayes' Theorem we can see the following {I: Indian, T: Thai, b: better, c: chosen)


		p(Ib|Tc) = p(Tc|Ib)p(Ib) / p(Tc|Ib)p(Ib) + p(Tc|Tb)p(Tb)

		p(Ib|Tc) = (0.33 * 0.66) / (0.33 * 0.66) + (0.66 * 0.33)

		p(Ib|Tc) = 0.5


An information cascade will occur when public evidence outweighs private belief. Say Both Alice and Bob chose Thai, while Charlie believes Indian is better.  What is the rational choice for Charlie? Thai of course!  To see why, let's call upon the Rev Tom...


		p(Ib|TcTc) = p(TcTc|Ib)p(Ib) / p(TcTc|Ib)p(Ib) + p(TcTc|Tb)p(Tb)

		p(Ib|TcTc) = (0.33^2 * 0.66) / (0.33^2 * 0.66) + (0.66^2 * 0.33)

		p(Ib|TcTc) = 0.33

Despite having a private credence of 66% that Indian was better, evidence from the earlier choices of others means that a rational Bayesian should reject their initial belief.  This obviously will continue for any other people choosing later.

Here's Welch on this phenomena:

> Erroneous Mass Behavior: In an information cascades everyone is individually acting rationally. Still, even if all participants as a collective have overwhelming information in favour of the correct action, each and every participant may take the wrong action. The probability that everyone is taking the wrong action is less than 50%, but it is easy to construct examples in which everyone is wrong with 30-40% probability.
>
> Fragility: A little bit of public information (or an unusual signal) can overturn a long-standing informational cascades. That is, even though a million people may have chosen one action, seemingly little information can induce the next million people to choose the opposite action. Fragility is an integral component of the Informational cascades theory!

What we can see then is that an information requires the following ingredients:

- Agents make decisions sequentially
- Agents make decisions rationally based on the information they have
- Agents do not have access to the private information of others
- A limited action space exists (e.g. an adopt/reject decision)

So in this workshop, we are going to simulate information cascades in an agent-based-model.  To [the code](simulation.coffee.md) Batman....