# FE style guide

A people problem.

There are lots of FE style guides, and ideas about how to build them.

Outline acceptable usage.

Similar to jslint: what if we had a design linter?

**Greenfield project**: a project that lacks constraint by prior work.

But most development is "brownfield" work. There's toxic waste everywhere.


## The DOM - how we make an audit of our site

We turn to `phantomjs` and script duplication of elements and then display the copied elements, with their directly-applied style, and compare the display of "similar" elements out of page context.

Lots of times the same element will display differently--style implementations are different

Style guide is a contract you write with the design team. When you deviate it's an explicit deviation.


## Scaffolding

Build a temporary structure to build the real structure.


## The answer: web components

Element as primitive.

- hides implementation details
- unifies implementation details

Statically typed design.
