# animation

60 fps is the target rate.. so you have 16.66 ms per frame

In a browser--all sorts of additional stuff happening that we have no control over

- no garbage collection tuning (i.e., you can't tell the browser "wait until I have around 10MB of storage before you start cleaning it up")
- no microtask semantics - delivery of events
- no execution scheduling - how long something will take

## Solution: web workers

Make single-threaded JS multithreaded.

    var worker = new Worker('path/to/some.js');

    worker.onmessage = function(ev) { ... }

Inside a worker you have some standard stuff:
- `setTimeout`
- `setInterval`
- `new Date()`
etc.

keys:

`browserify`, `webworkify`

Try to condense messages between threads into one instead of a bunch--having a bunch going back and forth can greatly degrade performance.


## Entity system

factory pattern

- `readFromSnapshot`: entity accepts date
- `writeToSnapshot`: serializing an object


### Interpolation

- we're always rendering one step in the past--this is how all games/animations/etc work.
- save the last two snapshots and interpolate to figure out states between them
