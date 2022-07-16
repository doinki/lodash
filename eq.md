```js
var object = { a: 1 };
var other = { a: 1 };

_.eq(object, object);
// => true

_.eq(object, other);
// => false

_.eq('a', 'a');
// => true

_.eq('a', Object('a'));
// => false

_.eq(NaN, NaN);
// => true

function eq(value, other) {
  return value === other || (value !== value && other !== other);
}
```

```js
// NaN
value !== value && other !== other;
```
