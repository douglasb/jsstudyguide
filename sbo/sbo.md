## Standard Built in Objects (SBO)

### Object
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object

### Object.entries()

Object.entries() returns an array whose elements are arrays corresponding to the enumerable string-keyed property [key, value] pairs found directly upon object. The ordering of the properties is the same as that given by looping over the property values of the object manually.

The Object.entries() method returns an array of a given object's own enumerable string-keyed property [key, value] pairs, in the same order as that provided by a for...in loop (the difference being that a for-in loop enumerates properties in the prototype chain as well). The order of the array returned by Object.entries() does not depend on how an object is defined. If there is a need for certain ordering then the array should be sorted first like Object.entries(obj).sort((a, b) => b[0].localeCompare(a[0]));.

``` 
const object1 = {
  a: 'somestring',
  b: 42
};

for (let [key, value] of Object.entries(object1)) {
  console.log(`${key}: ${value}`);
}

// expected output:
// "a: somestring"
// "b: 42"
// order is not guaranteed

```


### Set

The Set object lets you store unique values of any type, whether primitive values or object references.

Set objects are collections of values. You can iterate through the elements of a set in insertion order. A value in the Set may only occur once; it is unique in the Set's collection.

``` 
const set1 = new Set([1, 2, 3, 4, 5]);

console.log(set1.has(1));
// expected output: true

console.log(set1.has(5));
// expected output: true

console.log(set1.has(6));
// expected output: false

```
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set


##
### Set.prototype.has()

The has() method returns a boolean indicating whether an element with the specified value exists in a Set object or not.


``` 
const set1 = new Set([1, 2, 3, 4, 5]);

console.log(set1.has(1));
// expected output: true

console.log(set1.has(5));
// expected output: true

console.log(set1.has(6));
// expected output: false

```
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/has