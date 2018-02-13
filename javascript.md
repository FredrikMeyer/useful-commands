# Javacript

## Spread operator (ES6)

For applying a list of arguments to a function:

```javascript
function myFunction(x, y, z) { }
const args = [0, 1, 2];
myFunction(...args);
```
(from the [Mozilla docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax))

In object definitions:
```javascript
const myList = [1,2,3,4]
const [first, ...rest] = myList
```

Now `first` is `1` and `rest` is `[2,3,4]`.
