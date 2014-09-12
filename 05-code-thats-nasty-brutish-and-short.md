### Computational Philosophy Workshop

# Code that's Nasty, Brutish, and Short


		Nature::state () ->
			["solitary", "poore", "nasty", "brutish", "short"]


This week we dive into political theory with an examination of Hobbes' state of nature.  Hobbes' major project, according to [Lloyd & Sreedha][sep], was to "discover rational principles for the construction of a civil polity that would not be subject to destruction from within." 

[sep]: http://plato.stanford.edu/entries/hobbes-moral/

## A little on Hobbes

- 5 Apr 1588 - 4 Dec 1679
- Born to a Vicar, raised by a wealthy uncle
- Studied at Oxford
- Famous works include a number of Greek to English translation as well as his own De Cive, De Corpore, De Homine, & Leviathan

Hobbes thought that any political authority that wasn't absolute was systematically prone to dissolution and civil war.  He was searching for an account of political stability.  In game theory terms, he was searching for a stable equilibrium. 

So what is the best payoff matrix to describe Hobbes' account of the state of nature?  Identifying one is the primary goal for this week's workshop.  We will attempt to construct a set of utility functions and player strategies that replicate a _warre of all against all_ in an evolutionary state, before exploring some other plausible stable alternatives.


## Aims

- What is the most accurate payoff matrix for the state of nature according to Hobbes?
- Does this create "a warre of all against all" as Hobbes predicted?
- What is the most charitable model we can make that realises Hobbes' predictions?


Hobbes' argument for the Leviathan seems to be one from necessity.  That the state of nature is so bad that every rational agent would willingly submit to an absolute sovereign.  His argument might go something like this:

1. Agents are motivated purely by self interest (note this self interest is not necessarily rational)

2. Agents in the state of nature are sufficiently equal to harm or betray any other agent.

3. Social cooperation for mutual advantage requires that agents honour their covenants.

4. Because of 1 & 2, 3 is not possible.

5. Therefore the state of nature is not one of mutual advantage.

6. A state of mutual advantage can be realised by submitting to a Leviathan

7. Mutual advantage under a Leviathan is preferable to the state of nature.

8. Therefore rational agents would prefer the Leviathan (from 5, 6, & 7)



## Reading

[Hobbes' Moral and Political Philosophy](http://plato.stanford.edu/entries/hobbes-moral/)

_Leviathan_ Ch [13][13], [14][14], & [15][15]

[13]: https://ebooks.adelaide.edu.au/h/hobbes/thomas/h68l/chapter13.html

[14]: https://ebooks.adelaide.edu.au/h/hobbes/thomas/h68l/chapter14.html

[15]: https://ebooks.adelaide.edu.au/h/hobbes/thomas/h68l/chapter15.html



## Reading notes

### Chapter 13

> Nature hath made men so equal in the faculties of body and mind as that, though there be found one man sometimes manifestly stronger in body or of quicker mind than another, yet when all is reckoned together the difference between man and man is not so considerable as that one man can thereupon claim to himself any benefit to which another may not pretend as well as he. For as to the strength of body, the weakest has strength enough to kill the strongest, either by secret machination or by confederacy with others that are in the same danger with himself.  

> For there is not ordinarily a greater sign of the equal distribution of anything than that every man is contented with his share.

> if any two men desire the same thing, which nevertheless they cannot both enjoy, they become enemies; and in the way to their end (which is principally their own conservation, and sometimes their delectation only) endeavour to destroy or subdue one another.

> by force, or wiles, to master the persons of all men he can so long till he see no other power great enough to endanger him: and this is no more than his own conservation requireth, and is generally allowed.

> Again, men have no pleasure (but on the contrary a great deal of grief) in keeping company where there is no power able to overawe them all.

> So that in the nature of man, we find three principal causes of quarrel. First, competition; secondly, diffidence; thirdly, glory.
>
> The first maketh men invade for gain; the second, for safety; and the third, for reputation. The first use violence, to make themselves masters of other men's persons, wives, children, and cattle; the second, to defend them; the third, for trifles, as a word, a smile, a different opinion, and any other sign of undervalue, either direct in their persons or by reflection in their kindred, their friends, their nation, their profession, or their name.

> Hereby it is manifest that during the time men live without a common power to keep them all in awe, they are in that condition which is called war; and such a war as is of every man against every man.

> Whatsoever therefore is consequent to a time of war, where every man is enemy to every man, the same consequent to the time wherein men live without other security than what their own strength and their own invention shall furnish them withal. In such condition there is no place for industry, because the fruit thereof is uncertain: and consequently no culture of the earth; no navigation, nor use of the commodities that may be imported by sea; no commodious building; no instruments of moving and removing such things as require much force; no knowledge of the face of the earth; no account of time; no arts; no letters; no society; and which is worst of all, continual fear, and danger of violent death; and the life of man, solitary, poor, nasty, brutish, and short.

> To this war of every man against every man, this also is consequent; that nothing can be unjust. The notions of right and wrong, justice and injustice, have there no place. Where there is no common power, there is no law; where no law, no injustice.

> It is consequent also to the same condition that there be no propriety, no dominion, no mine and thine distinct; but only that to be every man's that he can get, and for so long as he can keep it.

> The passions that incline men to peace are: fear of death; desire of such things as are necessary to commodious living; and a hope by their industry to obtain them. And reason suggesteth convenient articles of peace upon which men may be drawn to agreement. These articles are they which otherwise are called the laws of nature.


### Chapter 14

> For where no covenant hath preceded, there hath no right been transferred, and every man has right to everything and consequently, no action can be unjust. But when a covenant is made, then to break it is unjust and the definition of injustice is no other than the not performance of covenant. And whatsoever is not unjust is just.

> Therefore before the names of just and unjust can have place, there must be some coercive power to compel men equally to the performance of their covenants, by the terror of some punishment greater than the benefit they expect by the breach of their covenant, and to make good that propriety which by mutual contract men acquire in recompense of the universal right they abandon: and such power there is none before the erection of a Commonwealth.

> So that the nature of justice consisteth in keeping of valid covenants, but the validity of covenants begins not but with the constitution of a civil power sufficient to compel men to keep them: and then it is also that propriety begins.

> The fool hath said in his heart, there is no such thing as justice, and sometimes also with his tongue, seriously alleging that every man's conservation and contentment being committed to his own care, there could be no reason why every man might not do what he thought conduced thereunto:

> that in a condition of war, wherein every man to every man, for want of a common power to keep them all in awe, is an enemy, there is no man can hope by his own strength, or wit, to himself from destruction without the help of confederates;

> He, therefore, that breaketh his covenant, and consequently declareth that he thinks he may with reason do so, cannot be received into any society that unite themselves for peace and defence but by the error of them that receive him; nor when he is received be retained in it without seeing the danger of their error; which errors a man cannot reasonably reckon upon as the means of his security: and therefore if he be left, or cast out of society, he perisheth; and if he live in society, it is by the errors of other men, which he could not foresee nor reckon upon, and consequently against the reason of his preservation; and so, as all men that contribute not to his destruction forbear him only out of ignorance of what is good for themselves.

> Whatsoever is done to a man, conformable to his own will signified to the doer, is not injury to him. For if he that doeth it hath not passed away his original right to do what he please by some antecedent covenant, there is no breach of covenant, and therefore no injury done him. And if he have, then his will to have it done, being signified, is a release of that covenant, and so again there is no injury done him.

> The value of all things contracted for is measured by the appetite of the contractors, and therefore the just value is that which they be contented to give. 

> To speak properly, commutative justice is the justice of a contractor; that is, a performance of covenant in buying and selling, hiring and letting to hire, lending and borrowing, exchanging, bartering, and other acts of contract.

> And distributive justice, the justice of an arbitrator; that is to say, the act of defining what is just. Wherein, being trusted by them that make him arbitrator, if he perform his trust, he is said to distribute to every man his own: and this is indeed just distribution, and may be called, though improperly, distributive justice, but more properly equity, which also is a law of nature, as shall be shown in due place.

> As justice dependeth on antecedent covenant; so does gratitude depend on antecedent grace; that is to say, antecedent free gift;

> For no man giveth but with intention of good to himself, because gift is voluntary; and of all voluntary acts, the object is to every man his own good; of which if men see they shall be frustrated, there will be no beginning of benevolence or trust, nor consequently of mutual help, nor of reconciliation of one man to another; and therefore they are to remain still in the condition of war, which is contrary to the first and fundamental law of nature which commandeth men to seek peace.

> A fifth law of nature is complaisance; that is to say, that every man strive to accommodate himself to the rest.

> For seeing every man, not only by right, but also by necessity of nature, is supposed to endeavour all he can to obtain that which is necessary for his conservation, he that shall oppose himself against it for things superfluous is guilty of the war that thereupon is to follow, ... The observers of this law may be called sociable, (the Latins call them commodi); the contrary, stubborn, insociable, forward, intractable.

> A sixth law of nature is this: that upon caution of the future time, a man ought to pardon the offences past of them that, repenting, desire it.

> that every man acknowledge another for his equal by nature. The breach of this precept is pride.

> at the entrance into conditions of peace, no man require to reserve to himself any right which he is not content should he reserved to every one of the rest. As it is necessary for all men that seek peace to lay down certain rights of nature; that is to say, not to have liberty to do all they list, so is it necessary for man's life to retain some: as right to govern their own bodies;

> if a man he trusted to judge between man and man, it is a precept of the law of nature that he deal equally between them. For without that, the controversies of men cannot be determined but by war.

> that such things as cannot he divided be enjoyed in common, if it can be; and if the quantity of the thing permit, without stint; otherwise proportionably to the number of them that have right.

> But some things there be that can neither be divided nor enjoyed in common. Then, the law of nature which prescribeth equity requireth: that the entire right, or else (making the use alternate) the first possession, be determined by lot. 

> they have been contracted into one easy sum, intelligible even to the meanest capacity; and that is: Do not that to another which thou wouldest not have done to thyself

> The laws of nature are immutable and eternal; for injustice, ingratitude, arrogance, pride, iniquity, acception of persons, and the rest can never be made lawful. For it can never be that war shall preserve life, and peace destroy it.

> And therefore so long as a man is in the condition of mere nature, which is a condition of war, private appetite is the measure of good and evil: and consequently all men agree on this, that peace is good, and therefore also the way or means of peace, which (as I have shown before) are justice, gratitude, modesty, equity, mercy, and the rest of the laws of nature, are good;


### Chapter 15

> And as the right of possession is called dominion so the right of doing any action is called authority.

> when the actor maketh a covenant by authority, he bindeth thereby the author no less than if he had made it himself; and no less subjecteth him to all the consequences of the same. 

> And he that maketh a covenant with the author, by mediation of the actor... is no longer obliged: for the covenant made with the author is not valid without his counter-assurance.  But if he that so covenanteth knew beforehand he was to expect no other assurance than the actor's word, then is the covenant valid, because the actor in this case maketh himself the author.

> And because the multitude naturally is not one, but many, they cannot be understood for one, but in any authors, of everything their representative saith or doth in their name; every man giving their common representer authority from himself in particular, and owning all the actions the representer doth, in case they give him authority without stint: otherwise, when they limit him in what and how far he shall represent them, none of them owneth more than they gave him commission to act.

> And if the representative consist of many men, the voice of the greater number must be considered as the voice of them all. 

### Chapter 16

The final cause, end, or design of men (who naturally love liberty, and dominion over others) in the introduction of that restraint upon themselves, in which we see them live in Commonwealths, is the foresight of their own preservation, and of a more contented life thereby; that is to say, of getting themselves out from that miserable condition of war which is necessarily consequent, as hath been shown, to the natural passions of men when there is no visible power to keep them in awe, and tie them by fear of punishment to the performance of their covenants, and observation of those laws of nature set down in the fourteenth and fifteenth chapters.