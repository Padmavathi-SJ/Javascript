### 01] 2667. Create Hello World Function:
**Write a function createHelloWorld. It should return a new function that always returns "Hello World".**

```
/**
 * @return {Function}
 */
var createHelloWorld = function() {
    
    return function(...args) {
        return 'Hello World'
    }
};

/**
 * const f = createHelloWorld();
 * f(); // "Hello World"
 */
```

### 02] 2620. Counter:
**Given an integer n, return a counter function. This counter function initially returns n and then returns 1 more than the previous value every subsequent time it is called (n, n + 1, n + 2, etc).**

```
/**
 * @param {number} n
 * @return {Function} counter
 */
var createCounter = function(n) {
    
    return function() {
        return n++;
    
    };
    
};

/** 
 * const counter = createCounter(10)
 * counter() // 10
 * counter() // 11
 * counter() // 12
 */
```

### 03] 2704. To Be Or Not To Be:
**Write a function expect that helps developers test their code. It should take in any value val and return an object with the following two functions.**
**toBe(val) accepts another value and returns true if the two values === each other. If they are not equal, it should throw an error "Not Equal".**
**notToBe(val) accepts another value and returns true if the two values !== each other. If they are equal, it should throw an error "Equal".**

```
/**
 * @param {string} val
 * @return {Object}
 */
var expect = function(val) {
    return {
        toBe:(val2)=>{
            if(val!==val2)throw new Error("Not Equal");
            else return true;
        }
        ,
        notToBe:(val2)=>{
            if(val===val2) throw new Error("Equal");
            else return true;
        }
    }
};

/**
 * expect(5).toBe(5); // true
 * expect(5).notToBe(5); // throws "Equal"
 */
```

### 04] 2665. Counter II
**Write a function createCounter. It should accept an initial integer init. It should return an object with three functions.**
**The three functions are:**

**increment() increases the current value by 1 and then returns it.**
**decrement() reduces the current value by 1 and then returns it.**
**reset() sets the current value to init and then returns it.**

```
var createCounter = function(init) {
  let presentCount = init;

  function increment() {
    return ++presentCount;
  }

  function decrement() {
      return --presentCount;
  }

  function reset() {
      return (presentCount = init);
  }

  return { increment, decrement, reset };
};
```
### 05]. 2635. Apply Transform Over Each Element in Array
**Given an integer array arr and a mapping function fn, return a new array with a transformation applied to each element.**

**The returned array should be created such that returnedArray[i] = fn(arr[i], i).**

**Please solve it without the built-in Array.map method.**

```
/**
 * @param {number[]} arr
 * @param {Function} fn
 * @return {number[]}
 */
var map = function(arr, fn) {
    for(let i=0;i<arr.length;i++){
        arr[i]=fn(arr[i],i);
    }
    return arr
};
```

### 06]. 2634. Filter Elements from Array

**Given an integer array arr and a filtering function fn, return a filtered array filteredArr.**

**The fn function takes one or two arguments:**

**arr[i] - number from the arr
i - index of arr[i]
filteredArr should only contain the elements from the arr for which the expression fn(arr[i], i) evaluates to a truthy value. A truthy value is a value where Boolean(value) returns true.**

**Please solve it without the built-in Array.filter method.**

```
/**
 * @param {number[]} arr
 * @param {Function} fn
 * @return {number[]}
 */
var filter = function(arr, fn) {
    let fil=[]
    for(let i=0;i<arr.length;i++){
        if(fn(arr[i],i)){
            fil.push(arr[i]);
        }
    }
    return fil
};
```


### 07]. 2626. Array Reduce Transformation
**Given an integer array nums, a reducer function fn, and an initial value init, return the final result obtained by executing the fn function on each element of the array, sequentially, passing in the return value from the calculation on the preceding element.**

**This result is achieved through the following operations: val = fn(init, nums[0]), val = fn(val, nums[1]), val = fn(val, nums[2]), ... until every element in the array has been processed. The ultimate value of val is then returned.**

**If the length of the array is 0, the function should return init.**

**Please solve it without using the built-in Array.reduce method.**

```
/**
 * @param {number[]} nums
 * @param {Function} fn
 * @param {number} init
 * @return {number}
 */
var reduce = function(nums, fn, init) {
     let val = init;
  for (let i = 0; i < nums.length; i++) {
    val = fn(val, nums[i]);
  }
  return val;
};
```

### 06]. 2629. Function Composition
**Given an array of functions [f1, f2, f3, ..., fn], return a new function fn that is the function composition of the array of functions.**
**The function composition of [f(x), g(x), h(x)] is fn(x) = f(g(h(x))).**
**The function composition of an empty list of functions is the identity function f(x) = x.**
**You may assume each function in the array accepts one integer as input and returns one integer as output.**

```
/**
 * @param {Function[]} functions
 * @return {Function}
 */
var compose = function(functions) {
    n=functions.length;
    return function(x) {
        if(n==0){
            return x;
        }
        else {
            result =x;
            for(let i=n-1; i>=0; i--){
                result=functions[i](result);
            }
            return result;
        }
        
    }
};

/**
 * const fn = compose([x => x + 1, x => 2 * x])
 * fn(4) // 9
 */
```

### 07]. 2703. Return Length of Arguments Passed

**Write a function argumentsLength that returns the count of arguments passed to it.**
**Input: args = [5]
Output: 1**

```
/**
 * @param {...(null|boolean|number|string|Array|Object)} args
 * @return {number}
 */
var argumentsLength = function(...args) {
    return args.length;
};

/**
 * argumentsLength(1, 2, 3); // 3
 */
```

###
 
