```js
/**
 * Checks if `value` is likely an `arguments` object.
 *
 * @static
 * @memberOf _
 * @since 0.1.0
 * @category Lang
 * @param {*} value The value to check.
 * @returns {boolean} Returns `true` if `value` is an `arguments` object,
 *  else `false`.
 * @example
 *
 * _.isArguments(function() { return arguments; }());
 * // => true
 *
 * _.isArguments([1, 2, 3]);
 * // => false
 */
var isArguments = baseIsArguments(
  (function () {
    return arguments;
  })()
)
  ? baseIsArguments
  : function (value) {
      return (
        isObjectLike(value) &&
        hasOwnProperty.call(value, 'callee') &&
        !propertyIsEnumerable.call(value, 'callee')
      );
    };
```

baseIsArguments가 동작하지 않는 경우는 언제일까?

- [propertyIsEnumerable](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Object/propertyIsEnumerable)
