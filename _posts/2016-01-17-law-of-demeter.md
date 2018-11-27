---
layout: post
title:  "The Law of Demeter in Spanish"
subtitle: "some thoughts on natural and programming languages"
date:   2016-01-17 18:13:04

categories: [code]
---

Here I want to write about how a simple language construction which we take for granted translates into a foundational principle of good object-oriented code which, while well-understood by many programmers, is not always known intuitively.

I was trying to construct a sentence referencing my mother-in-law's jacket. Of course, with some basic Spanish it's not that hard: you just need the appropriate basic nouns and knowledge of how to describe possession, which most Americans can already grok:

> la chaqueta de la madre de mi esposa

Of course, chaining possessives like this is 'no bueno.' It's akin to saying in English, "the jacket of the mother of my wife" -- while not grammatically incorrect, it's clumsy and awkward when spoken aloud. A Spanish teacher might just say "no, that's wrong, try this," but we programmers have another lens with which to describe what's wrong with it. 

Enter the Law of Demeter.

~~~~
The Law of Demeter (LoD) or principle of least knowledge is a design guideline for developing software, particularly object-oriented programs. In its general form, the LoD is a specific case of loose coupling. The guideline was proposed at Northeastern University towards the end of 1987, and can be succinctly summarized in each of the following ways:

1. Each unit should have only limited knowledge about other units: only units "closely" related to the current unit.

2. Each unit should only talk to its friends; don't talk to strangers.

3. Only talk to your immediate friends.

(source: Wikipedia)
~~~~

This is fine and good for a technical definition, but when it comes to most programming concepts, we want to internalize. We want second-nature. I don't just want to know why LoD violations are incorrect, technically; I want to *feel* their incorrectness in the same way I feel that "the jacket of the mother of my wife" is awkward.

There is something about using a natural language analogy to describe a programming language concept that gets straight to its root. Perhaps because natural language is such a central part of and so thoroughly understood to us as humans, the point is made clear in the comparison. 

Even if this sort of analogy is not immediately useful to us, it is extremely useful as a teaching tool. Try explaining the Law of Demeter to your non-technical friends using the description on Wikipedia; then try using natural language as an analogy, and see which one sticks.

Okay, so the concept of the Law of Demeter in natural languages and programming languages is fundamentally similar. What can we learn from this?

# La Suegra 

Let's try to improve our awkward construction. Thankfully, the Spanish language already has our back and offers a ready-made abstraction. The work "suegra" means mother-in-law, and carries with it all the same meaning.

> la chaqueta de mi suegra

Poof! Our construction is much less awkward, and better yet, more expressive.

Why not take it one step further? We can use the same technique and create another abstraction to boil down our construction to its essential essence.

> la suegreta

Okay, that didn't work. But why not?! We did the same thing! 

The word "suegreta," a portmanteau of "suegra" and "chaqueta" that I just made up, does not work because it lacks essential meaning *by itself*. Abstractions are only useful insofar as they describe something meaningful.

Similarly, when we correct LoD violations in our codebases, we must be careful not to overdo it. If you abstract away a relationship into a module or class that lacks meaning beyond that relationship, you may be putting a band aid on a compound fracture. That's a smell! Consider rethinking how the relationship itself is constructed.

# Hangry 

Natural languages, like programming languages, are fluid. While the essential building blocks are static in the long-term -- nouns and verbs in Spanish, classes and methods in Ruby, functions and types in Haskell -- the ways in which they are used are constantly changing. The dictionary, like any codebase, is constantly shifting and expanding.

Consider this past summer's quarterly update to the Oxford English dictionary; among the words added are 'awesomesauce', 'microaggression', 'subreddit' and 'hangry.' These words would have been meaningless to a year 2000 English language user, but are part of the 2015 user's essential vocabulary. Similarly, new abstractions are introduced to code as they acquire meaning or become useful in multiple places, and are removed as they lose meaning (just as some dictionaries periodically purge antiquated words).

Sure, one might say "she is angry because she is hungry," but the concept of 'hangry' now has enough standalone meaning to deserve its own official portmanteau. Compare this to Martin Fowler's 'Rule of Three' refactoring rule -- it's best to wait until the meaning behind an abstraction is well-understood before introducing it. 

# The In-Laws

One of the advantages to encapsulating meaning this way is that now the meaning is free to change. Programmers know the benefits of so-called "information-hiding." As long as the interface to a well-encapsulated module or class stays the same, the internal definition can change.

Consider the technical definition of the word "in-laws." Now consider the social meaning the word has acquired over the years. 

~~~~
In-law: Someone who will be a prime suspect after your murder. Usually mother-in-laws are the worst, not because of their hatred of you, but because they will question you to death.

Stereotypical veteran father-in-law: "Let me show you my M14."
 
Mother-in-law: "You should take better care of the kids, they're only 21 you know."

(source: UrbanDictionary.com)
~~~~

All of this new nuance, and the English language doesn't even have to slot in a new word!

Keep an eye out for more natural language analogies like this one. Thinking on this topic, I've come to realize that many of the new programming concepts which seem like great revelations at the time of learning have actually been sitting in front of us, used in our speech and writing every day.

