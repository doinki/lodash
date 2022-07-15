```js
_.isObject({});
// => true

_.isObject([1, 2, 3]);
// => true

_.isObject(_.noop);
// => true

_.isObject(null);
// => false
```

```js
function isObject(value) {
  var type = typeof value;
  return value != null && (type == 'object' || type == 'function');
}
```

*typeof undefined*는 **undefined**이지만 *typeof null*은 **object**이다.
