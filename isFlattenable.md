```js
/**
 * Checks if `value` is a flattenable `arguments` object or array.
 *
 * @private
 * @param {*} value The value to check.
 * @returns {boolean} Returns `true` if `value` is flattenable, else `false`.
 */
function isFlattenable(value) {
  return (
    isArray(value) ||
    isArguments(value) ||
    !!(spreadableSymbol && value && value[spreadableSymbol])
  );
}
```

_isConcatSpreadable_ 오...

- [isConcatSpreadable](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/isConcatSpreadable)
