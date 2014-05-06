# debugging

## Problems

Functions and closures are cool but can be hard to debug:

- Closures hide their state really well
- Can't monkey patch closures
- Partial applications and lazy evaluation are even harder to debug


## Best practices

- At least in development, make classes and objects accessible from the console.
  - check variable states when application in idle state
  - jump start processes from console: `app.emit('change')`

- live edit... maybe overhyped, but it has its uses
  problems:
    - major problem is there's no build step
    - can map to local filesystem, but not to a remote filesystem
    - locked into the devtools editor

With complex code, it becomes hard to know/remember what's touching what; hard to step debug, keep entire system in your head, etc:

- setting up "traps":
  - Break on method calls - e.g. add debugger statement in `Event.prototype`
  - Break on custom events:

        user.on('change', function(){
          debugger;
        });

  - Break on property access: use setters and getters
  - Break on callbacks - to make sure (or see when) an async process finishes
  - Break on DOM mutation (in the future) - DOM mutation events. You get an async call stack though (but this is gonna change in a future version of Chrome)
  - Break on object mutation.... maybe

        Object.observe

    - Break on property `add`, `change`, `delete`
    - async call stack (not working yet)


## Tools

### Command line API

Some undocumented APIs:

`debug(fn)`: sets breakpoint on function
`monitor(fn)`: logs whenever this function is called

Debug utils: [https://github.com/amasad/debug_utils]()


### fb-flo

live edit and reload, developed and open-sourced by facebook

[http://facebook.github.io/fb-flo/]()
