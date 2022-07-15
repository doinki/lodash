```js
_.isFunction(_);
// => true

_.isFunction(/abc/);
// => false
```

```js
function isFunction(value) {
  if (!isObject(value)) {
    return false;
  }
  // The use of `Object#toString` avoids issues with the `typeof` operator
  // in Safari 9 which returns 'object' for typed arrays and other constructors.
  var tag = baseGetTag(value);
  return tag == funcTag || tag == genTag || tag == asyncTag || tag == proxyTag;
}
```

*typeof function*을 사용하지 않고 **tag**를 사용한다.

주석에 나와있는 것처럼 Safari 9에서 이슈가 있나보다.
