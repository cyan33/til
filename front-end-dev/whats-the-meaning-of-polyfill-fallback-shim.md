### Polyfill

---

A polyfill is not part of the HTML5 Standard. Nor is a polyfill limited to Javascript, even though you often see polyfills being referred to in those contexts.

The term polyfill itself refers to some code that "allows you to have some specific functionality that you expect in current or “modern” browsers to also work in other browsers that do not have the support for that functionality built in. "

### Shim

---

A shim is a library that brings a new API to an older environment, using only the means of that environment.

Thus, a polyfill is a shim for a browser API. You typically check if a browser supports an API and load a polyfill if it doesn’t. That allows you to use the API in either case. 

### Fallback

---

Fallback usually replaces the feature with simplified functionality or third-party plugin or even error message. For example, if the browser does not support video tag, you can replace it with a flash plugin.