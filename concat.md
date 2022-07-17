```js
var array = [1];
var other = _.concat(array, 2, [3], [[4]]);

console.log(other);
// => [1, 2, 3, [4]]

console.log(array);
// => [1]

function concat() {
  var length = arguments.length;
  if (!length) {
    return [];
  }
  var args = Array(length - 1),
    array = arguments[0],
    index = length;

  while (index--) {
    args[index - 1] = arguments[index];
  }
  return arrayPush(
    isArray(array) ? copyArray(array) : [array],
    baseFlatten(args, 1)
  );
}
```
