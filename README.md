# Local Link

This function accepts a click event and returns the anchor element if the following conditions are met:

* The anchor host is the same as current page
* The anchor protocol is the same as current page
* The click was a left-click
* The click was not modified with shift, alt, ctrl, or meta
* The target attribute was not used, or targeted `_self`
* The default behavior has not already been prevented

These are the conditions usually checked before preventing the default behavior of a click-event, for the purpose of client-side routing.

## Install

```
npm install local-anchor
```

## Example
``` js
var localLink = require('local-link');

window.addEventListener('click', function (e) {
  var anchor = localLink(e);

  if (anchor) {
    e.preventDefault();
    console.log(anchor.href);
    router(anchor.pathname);
  }
});
```

## Credits

This is built off of the [catch-links](https://github.com/substack/catch-links) module by [James Halliday](https://github.com/substack).  The main difference between this module and catch-links is that catch-links handles the event-binding and calls preventDefault.  I needed more control over these aspects in my projects. Thanks substack!

## License

MIT