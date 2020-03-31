---
title: "The Local Lemma"
date: 2020-03-31
permalink: /posts/2020/01/The_Local_Lemma/
tags:
  - math
  - computer science
  - probability
  - algorithms
---

**I.**

_If you want to learn how to do something -- teach it._


Okay. I will try to teach you something.

A _literal_ is a _Boolean variable_ $x$ or the negation of a $x$ which we can just denote as $\bar{x}$. If you're a programmer, then you at least know that a Boolean is a True or False value. So, we can really just think of $x$ as something that yells at us: TRUE or FALSE. Is it raining today? True or false?

Let's say now we have two booleans, $x_1$ and $x_2$. A _conjunction_ of $x_1$ and $x_2$ is basically the formalist's way of saying "AND", and we denote it with $x_1 \land x_2$. So if $x_1$ is a Boolean for whether it's raining today, and $x_2$ is a Boolean for whether there's a cat in my house, the _conjunction_ is a TRUE or FALSE value that corresponds to whether these two things are happening at the _same time_. Rainy outside today, and cat in my house. So $x_1 \land x_2$ will evaluate to TRUE. If it's rainy, but there's no cat, then $x_1 \land x_2$ will evaluate to FALSE. Both $x_1$ and $x_2$ need to be True at the same time. If one is missing, then it's false.

There's a notion of "OR" in logic as well. We call it the _disjunction_. If we have the _disjunction_ of $x_1$ and $x_2$ then we write $x_1 \lor x_2$. Basically, if we want $x_1 \lor x_2$ to evaluate to TRUE, then we need *at least* one of either $x_1$ or $x_2$ to be TRUE. In this case, if it's raining outside, and there's *no* cat in my house, the disjunction $x_1 \lor x_2$ will still evaluate to TRUE.

Okay, nice, we have some literals. What can we do with them? Well, now we can form a _clause_. A clause is just an arbitrary _disjunction_ of some literals. So let's say $y$ is a clause. If we have some literals, say $x_1, x_2$ and $\bar{x_3}$ we might have a clause that looks like $y = x_1 \lor x_2 \lor \bar{x_3}$. Clauses are surprisingly arbitrary, we can use them to represent a variety of objects. For example, let's say we have a graph $G$ made of $3$ vertices: $u, v$ and $w$. $G$ is connected, whatever. Now we can form the clause $y$ representing the question: "Is any vertex in $G$ colored red?" Good question. Now if $x_i$ ($i \in $ { $1, 2, 3$ }) are three Booleans that represent whether each vertex $u$, $v$ and $w$ is red (respectively), it's pretty plain to see that if at least one of the $x_i$'s is TRUE, then the corresponding vertex is red. The answer to our question is "yes", and consequently the clause $y = x_1 \lor x_2 \lor x_3$ is going to evaluate to TRUE as well.

Okay, let's recap. Literals are just some variables $x \in$ { $True, False$ } and a clause $y$ is just a disjunction of a bunch of literals. Great. Now what?

**II.**

The _satisifiability_ (SAT) problem is when we take a bunch of clauses $y_1, y_2, ..., y_k$ and then take the _conjunction_ of them. 
