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

### 06]. 









### 05]. 2626. Array Reduce Transformation
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

### 06]. 
 
