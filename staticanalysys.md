# Static Analysis

JavaScript is dynamically and weakly typed, and it uses prototypal inherence, which makes people think it's hard to do static analysis on JS. But...


## Static analysis

### How it works

A set of techiques of code analysis based on formal methods performed *without running the code*.

1. Build an **abstract syntax tree** (AST)

   Feed code to a js parser to create an AST - essentially a programmatic description of the program

2. Analyze

3. Transform

4. Regenerate code - minification, uglification, optimization, etc.

Building an AST isn't the only way to analyze code. You could use:

- simple text-based methods
- parse progressively

### Querying Syntax Tree

Structural search and replace with `grasp.js`

`grasp '#x'` variable value

etc.

### Code style

check out EditorConfig

### Linting

Linting - helping to detect errors and potential problems

JSLint, JSHint, Closure Linter...

**ESLint** - provides hooks for customized rules

### Fixing results

**fixmyjs** - autofix lint results (can use jshint settings)

### Code metrics and visualization

ESCompex - can keep track of:

- lines of code
- avg number of params in function
- cyclomatic complexity - how much branching there is in your code
- complexity density

etc.

gives maintainability index

other tools:
complexity-report
plato

### Detecting duplicated code

Duplicated code is bad - more size, less maintainable

JScpd - only cares about code structure/behavior


## Dynamic analysis

### Code coverage

How do you know you've tested enough?

1. instrument your code
2. run your tests
3. verify all checkpoints were encountered

code coverage tools: jscoverage, blanketjs, istanbul

### autocomplete and jump to source with COLT

COLT:

- Creates static http server
- parses js file with parser and injects some code
- IDE plugin gets info fron script

### spy-js

trace javascript events

create proxy http server, inject special code, listen to events
