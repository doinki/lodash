```js
/** Used to detect unsigned integer values. */
var reIsUint = /^(?:0|[1-9]\d*)$/;

/**
 * Checks if `value` is a valid array-like index.
 *
 * @private
 * @param {*} value The value to check.
 * @param {number} [length=MAX_SAFE_INTEGER] The upper bounds of a valid index.
 * @returns {boolean} Returns `true` if `value` is a valid index, else `false`.
 */
function isIndex(value, length) {
  var type = typeof value;
  length = length == null ? MAX_SAFE_INTEGER : length;

  return (
    !!length &&
    (type == 'number' || (type != 'symbol' && reIsUint.test(value))) &&
    value > -1 &&
    value % 1 == 0 &&
    value < length
  );
}
```

```js
// length가 truthy해야 한다.
!!length;

// type이 symbol이 아니어야 하고 value는 integer이어야 한다.
// reIsUint.test(value)에 symbol을 전달할 경우 Uncaught TypeError: Cannot convert a Symbol value to a string 에러가 발생한다.
type != 'symbol' && reIsUint.test(value);

// value는 정수이어야 한다.
value % 1 == 0;
```
