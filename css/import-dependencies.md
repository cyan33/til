## How to Import Dependencies in CSS

Say you have installed lodash via npm, and you could do `import _ from 'lodash';` to get access to lodash.

But how do you do the similar thing in css?

```css
@import url('~fontawesome/fontawesome.css');
```

Explained:

The path `@import` of css is relative to the current directory. And adding `~` at the beginning tells the Webpack loader to treat it like a module. So as of module import, anything you could do with `js`, you could do that with `css`.
