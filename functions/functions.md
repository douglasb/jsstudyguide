## Apply()

The apply() method calls a function with a given this value, and arguments provided as an array (or an array-like object).

You can assign a different this object when calling an existing function. this refers to the current object, the calling object. With apply, you can write a method once and then inherit it in another object, without having to rewrite the method for the new object.

apply is very similar to call(), except for the type of arguments it supports. You use an arguments array instead of a list of arguments (parameters). With apply, you can also use an array literal, for example, func.apply(this, ['eat', 'bananas']), or an Array object, for example, func.apply(this, new Array('eat', 'bananas')).

```
Note: While the syntax of this function is almost identical to that of call(), the fundamental difference is that call() accepts an argument list, while apply() accepts a single array of arguments.

``` 
``` 
Note: When the first argument is undefined or null a similar outcome can be achieved using the array spread syntax.
```

``` 
var numbers = [5, 6, 2, 3, 7];

var max = Math.max.apply(null, numbers);

console.log(max);
// expected output: 7

var min = Math.min.apply(null, numbers);

console.log(min);
// expected output: 2

 ```

#### Using apply to append an array to another
Clever usage of apply allows you to use built-in functions for some tasks, that otherwise probably would have been written by looping over the array values. As an example here we are going to use Math.max/Math.min, to find out the maximum/minimum value in an array.
``` 
// min/max number in an array
var numbers = [5, 6, 2, 3, 7];

// using Math.min/Math.max apply
var max = Math.max.apply(null, numbers); 
// This about equal to Math.max(numbers[0], ...)
// or Math.max(5, 6, ...)

var min = Math.min.apply(null, numbers);

// vs. simple loop based algorithm
max = -Infinity, min = +Infinity;

for (var i = 0; i < numbers.length; i++) {
  if (numbers[i] > max) {
    max = numbers[i];
  }
  if (numbers[i] < min) {
    min = numbers[i];
  }
}
 ```
##  
## Call()

The call() allows for a function/method belonging to **one object** to be assigned and called for a different **object**.

call() provides a new value of this to the function/method. With call, you can write a method once and then inherit it in another object, without having to rewrite the method for the new object.


**Note**: While the syntax of this function is almost identical to that of apply(), the fundamental difference is that call() accepts an argument list, while apply() accepts a single array of arguments.


``` 
function Product(name, price) {
  this.name = name;
  this.price = price;
}

function Food(name, price) {
  Product.call(this, name, price);
  this.category = 'food';
}

console.log(new Food('cheese', 5).name);
// expected output: "cheese"

 ```
