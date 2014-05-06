# Javascript apps as a build artifact

Why does it matter?

We're writing more complex (and just more) Javascript.


## 'Javascript battlefields'

1. "My framework is better than yours"
2. "My build tool is better than yours"
3. Languages that compile to JS
4. "My dependency management tool is better than yours"

And then you need to make it work with mobile app views--e.g. phonegap, cordova


## Attempt 1: Put all the things in git (or any VCS)

Good:

- easy workflow.. just commit
- easy mobile builds: just `git clone`

Bad:

- git submodules are hard to deal with
- merge conflict hell
- compiled code shouldn't be in VCS


## Attempt 2: NPM

You can run a shell script with a build

But npm that pulls a package from git didn't quite work either


## Attempt 3: JS as build artifact: github release API

A "release" in GitHub is just a tag and an a collection of binary blobs

Just need to curl and unzip, making putting it in anything downstream that needs to consume the app (i.e. native mobile app) really easy

Add a build step in XCode/Android Studio that pulls it from GitHub release API.

[http://blog.pagerduty.com/2014/05/reliable-mobile-build/]()
