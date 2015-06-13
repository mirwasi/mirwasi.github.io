---
layout: post
title: Introduction to Systems [Lecture 1 - MIT 6.033]
---

### What is a system? ###

>"A set of interconnected components that has an expected behavior observed at the interface with its environment”.

Complexity makes designing system very difficult.

### What does complexity mean? How does one define complexity? ###

A complex system has got:

- **large number** of components and connections.
- **irregular** design.
- a design that is **difficult to describe**.
- a design that takes **a lot of people** to maintain.



One metric to measure the complexity of a system is the _number of lines of code_. It’s not the best metric, but gives a rough estimation. (Facebook’s front end alone has 62-million lines of code!)

**The more the lines of code, the more complex the system it creates.**

More complexity:

- **limits** what we can build.
- more **expensive**.
- **harder** to maintain.
- easier to **break**.


The <a href="https://en.wikipedia.org/wiki/Worse_is_better#The_MIT_approach">MIT approach</a> leads to more complex designs, since it puts the least priority on simplicity.

###Problems created by complexity:###

- **New properties** emerges when components are **joined together**:
These properties are not evident when components are seen as individuals. When components are glued together to build a system, newer properties emerges.

- Small designs **don’t work very well at scale**.

- **Small changes** to to system lead to surprisingly **large after effects**.

### Mitigation of complexity: Modularity and abstraction! ###

Modular systems are divided into **components, or modules**, such that we can
consider the implementation and interfaces of these modules
**separately**.

_Example_: We don't need to know how a transistor works in order to program, or how assembly language works to use Java, or how Java works to use a word processor implemented in it.

Modular systems are:

- **easier** to reason about, change/improve and manage.
- modules **fail independently**.

### Common modularity/abstraction techniques: ###

1. **Layering**:

     _Example_: network protocols. Any layer can be built/modified without caring about the others.
2. **Hierarchy**:

     _Example_: routing.

## Types of modularity: ##

1. **Soft modularity:**  A type of modularity where the modules have to **follow a contract** that has a set of rules in which the modules are **not suppose to violate**.

	_Example:_ Modularization by functions. Functions must be implemented/used in the stated way. Otherwise, bad things can happedn.

2. **Enforced modularity:** A type of modularity where the modules are **prevented from violating the rules** by **implementing self-protecting codes** that protect a module’s integrity. 

	_Example:_ Client/Server modularity, virtualization.

## Conclusion ##
- The **bigger** the system gets, the **more complex** it becomes.
- Modularity and abstraction can **reduce the complexity** of a system.
- Getting **correct** modularity/abstraction is a **challenge**.
- Modularity **should be enforced**.


