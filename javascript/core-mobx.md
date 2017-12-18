# Core Concepts in MobX

* Use the `@observable` decorator or `observable(object or array)` functions to make objects trackable for MobX.
* The `@computed` decorator can be used to create functions that can automatically derive their value from the state.
* Use `autorun` to automatically run functions that depend on some observable state. This is useful for logging, making network requests, etc.
* Use the `@observer` decorator from the mobx-react package to make your React components truly reactive. They will update automatically and efficiently. Even when used in large complex applications with large amounts of data.
