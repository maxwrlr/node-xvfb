node-xvfb: easily start and stop an X Virtual Frame Buffer from your node apps.
-----

### Usage

```javascript
var Xvfb = require('xvfb');
var xvfb = new Xvfb();
xvfb.startSync();

// code that uses the virtual frame buffer here

xvfb.stopSync();
// the Xvfb is stopped
```

or:


```javascript
var Xvfb = require('xvfb');
var xvfb = new Xvfb();
xvfb.start(function(err, xvfbProcess) {
  // code that uses the virtual frame buffer here
  xvfb.stop(function(err) {
    // the Xvfb is stopped
  });
});
```

The Xvfb constructor takes two options:

* <code>displayNum</code> - the X display to use, defaults to the lowest unused display number >= 99 if <code>reuse</code> is false or 99 if <code>reuse</code> is true.
* <code>reuse</code> - whether to reuse an existing Xvfb instance if it already exists on the X display referenced by displayNum

### Thanks to

* [kesla](https://github.com/kesla) for https://github.com/kesla/node-headless
* [leonid-shevtsov](https://github.com/leonid-shevtsov) for https://github.com/leonid-shevtsov/headless

both of which served as inspiration for this package.
