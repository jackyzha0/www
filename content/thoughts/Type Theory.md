---
title: Type Theory
date: 2023-12-19
tags:
  - seed
---
See also: [[thoughts/functional programming|functional programming]]

[Source](https://ericnormand.me/article/church-vs-curry-types)
## Church Types
Also called intrinsic types.

In a Church-style system, types are an intrinsic part of the [[thoughts/semantics|semantics]] of the language. The language would be different without the types---it may even be meaningless. 

Intrinsic types are great because you are guaranteed to have a mathematically-sound safety net at all times.

e.g. Haskell

The Church typist argues that untyped programs are a subset of typed programs. They are programs that have a single type `any` and all values are of that one type. So instead of being liberating, dynamic languages restrict you to one type.
## Curry Types
Also called extrinsic types.

Curry-style types is when a system of types is applied that is not part of the semantics of the language.

Extrinsic types are great because you can apply multiple type systems to your code and also write things that you don't know how to prove are sound.

e.g. TypeScript / Python type annotations

The Curry typist argues that well-typed programs are a subset of dynamically typed programs. In other words, well-typed programs are just dynamic programs that are checked for type errors.

## Variance
Variance is how subtyping between more complex types relates to subtyping between their components.

 For any following code examples, assume you have a type `A` and a subtype `B` that inherits from `A`.

- Covariant if the type preserves the ordering of types (≤), which orders types from more specific to more generic
	- In the context of functions: something takes a parameter `A` can also take `B`.
- Contravariant if the type reverses this ordering
	- It occurs when a type system allows a function to accept a less derived type than originally specified.
	- This is mostly used in the context of function types (i.e. types of named and anonymous functions).
	- A function with type `(A -> T)` can always be assigned to something that takes a type `(B -> T)`
		- Imagine a function with signature `feed: (creature: Dog) => void`
		- You can always pass a more generic function `feed: (creature: Animal) => void` in its place
	- When dealing with functions that have multiple input types, contravariance applies to each parameter individually
