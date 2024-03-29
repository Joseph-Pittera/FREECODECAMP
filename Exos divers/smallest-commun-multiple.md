---
id: ae9defd7acaf69703ab432ea
title: Smallest Common Multiple
challengeType: 1
forumTopicId: 16075
dashedName: smallest-common-multiple
---

# --description--

Find the smallest common multiple of the provided parameters that can be evenly divided by both, as well as by all sequential numbers in the range between these parameters.

The range will be an array of two numbers that will not necessarily be in numerical order.

For example, if given 1 and 3, find the smallest common multiple of both 1 and 3 that is also evenly divisible by all numbers *between* 1 and 3. The answer here would be 6.

# --hints--

`smallestCommons([1, 5])` should return a number.

```js
assert.deepEqual(typeof smallestCommons([1, 5]), 'number');
```

`smallestCommons([1, 5])` should return 60.

```js
assert.deepEqual(smallestCommons([1, 5]), 60);
```

`smallestCommons([5, 1])` should return 60.

```js
assert.deepEqual(smallestCommons([5, 1]), 60);
```

`smallestCommons([2, 10])` should return 2520.

```js
assert.deepEqual(smallestCommons([2, 10]), 2520);
```

`smallestCommons([1, 13])` should return 360360.

```js
assert.deepEqual(smallestCommons([1, 13]), 360360);
```

`smallestCommons([23, 18])` should return 6056820.

```js
assert.deepEqual(smallestCommons([23, 18]), 6056820);
```

# --seed--

## --seed-contents--

```js
function smallestCommons(arr) {
  return arr;
}

smallestCommons([1,5]);
```

# --solutions--

```js
function smallestCommons(arr) {
  let arr2 = [];
  for (let i = Math.min(...arr); i <= Math.max(...arr); i++) {
    arr2.push(i);
  }
  let mult = 1;
  while (true) {
    if (arr2.every(x => mult % x == 0)) return mult;
    mult ++;
  }
}
```