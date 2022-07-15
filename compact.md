```js
_.compact([0, 1, false, 2, '', 3]);
// => [1, 2, 3]

function compact(array) {
  var index = -1,
    length = array == null ? 0 : array.length,
    resIndex = 0,
    result = [];

  while (++index < length) {
    var value = array[index];
    if (value) {
      result[resIndex++] = value;
    }
  }
  return result;
}
```

```js
false.length;
// => undefined

(0).length;
// => undefined

''.length;
// => 0

BigInt(0).length;
// => undefined

Symbol().length;
// => undefined
```

_(0).length_ 에서 괄호를 하지 않으면 **SyntaxError** 를 throw한다.

파싱할 때 소수점으로 판단해서 그런 것 같다.
