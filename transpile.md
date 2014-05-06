# ECMAScript 6 and beyond

Import some utilities and parse the code - build up an abstract syntax tree

**recast** - AST module

require, create AST, and perform arbitrary source transformations

> Non-destructive partial source transformation

Ariya Hidayat


Programming languages are notoriously difficult to "fix forward." Consider Python 3 - even though it's great, barely anyone is using it.

So how can ECMA 6 avoind the Python 3 trap?

Ease into the new language by simulating its most useful features in ECMA 5.

Always be transpiling.

E.g., `=>` function syntax. Build into your build step.

generator functions, and, the next step, async functions (with `await` keyword)
