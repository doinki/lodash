```js
_.isArrayLike([1, 2, 3]);
// => true

_.isArrayLike(document.body.children);
// => true

_.isArrayLike('abc');
// => true

_.isArrayLike(_.noop);
// => false
```

```js
function isArrayLike(value) {
  return value != null && isLength(value.length) && !isFunction(value);
}
```

- value는 null 또는 undefined가 아니어야 한다.
- value는 length property를 가져야 한다.
- value는 function이 아니어야 한다.
