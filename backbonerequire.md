# single page apps backbone.marionette and requirejs

## marionette

[http://marionettejs.com/]()

Utilities to help with organization


## modular design tips

**idempotent**

keep scopes super narrow: views should only deal with themselves

views should use

    this.listenTo( [...] )

instead of

    this.model.on( [...] )

If you have to use global listeners, e.g. window `resize`, make sure you unbind and namespace events


## r.js

resolves dependency tree and concatenates into a single file

see also: `almondjs`, a stripped-down version of `require.js`
