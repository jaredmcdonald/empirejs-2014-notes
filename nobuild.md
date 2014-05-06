# 'No-build-system build system'

## Development lifecycle

- boilerplate/bootstrapping
- package manager
- development iterations (this is where all the manual work is; everything else is automatable)
- build & optimiziation
- deployment

So we need to keep the development iterations lean and fast.


## Development loop

- editor
- authoring abstractions
- livereload
- browser

Immediacy is key.


## Why a build system?

**Transport.**

- bandwidth
- latency

development code `!==` production code

No build system in development

### Grunt

input --> do something (configuration) --> output

`Gruntfile`s can get very big

### Gulp

input --> task --> task --> task --> output

### Unix tool wrappers

- make
- jake
- rake
- ant
- maven

etc.


### But a website is different

A website is a *dependency graph*.

Doesn't fit well with the paradigm of dealing with lists of files.

Other programming languages have strict conventions and don't have to deal with the concept of transport

Problems:

- discovery
- coherence

Transport details end up leaking to development:

- file renaming
- bundling
- spriting
- compression

Something's missing...


## The solution

Use the source, just like the browser.

**AssetGraph**

[https://github.com/assetgraph/assetgraph]()

`assetgraph-builder`: an opinionated boilerplate

Solves the problem of discovery--essentially a scraper

reduces configuration

Solves coherence--knows about references to files and renaming happens automatically

dev website --> (transforms) --> production website
