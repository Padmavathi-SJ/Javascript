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

### 08]. 2629. Function Composition
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

### 09]. 2703. Return Length of Arguments Passed

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

### 10]. 2666. Allow One Function Call

**Given a function fn, return a new function that is identical to the original function except that it ensures fn is called at most once.
The first time the returned function is called, it should return the same result as fn.
Every subsequent time it is called, it should return undefined.**

 ```
/**
 * @param {Function} fn
 * @return {Function}
 */
var once = function (fn) {
    let counter = 0
    return function (...args) {
        counter++
        if (counter === 1) return fn(...args)
    }
};

/**
 * let fn = (a,b,c) => (a + b + c)
 * let onceFn = once(fn)
 *
 * onceFn(1,2,3); // 6
 * onceFn(2,3,6); // returns undefined without calling fn
 */
```

### 11]. 2623. Memoize
**Given a function fn, return a memoized version of that function.
A memoized function is a function that will never be called twice with the same inputs. Instead it will return a cached value.
You can assume there are 3 possible input functions: sum, fib, and factorial.
sum accepts two integers a and b and returns a + b. Assume that if a value has already been cached for the arguments (b, a) where a != b, it cannot be used for the arguments (a, b). For example, if the arguments are (3, 2) and (2, 3), two separate calls should be made.
fib accepts a single integer n and returns 1 if n <= 1 or fib(n - 1) + fib(n - 2) otherwise.
factorial accepts a single integer n and returns 1 if n <= 1 or factorial(n - 1) * n otherwise.**

```
/**
 * @param {Function} fn
 * @return {Function}
 */
function memoize(fn) {
 const map = new Map();
    return function(...args) {
        if(!map.has(JSON.stringify(args))){
            const b = fn(...args);
            map.set(JSON.stringify(args), b);
            return b;
        }
        else{
            return map.get(JSON.stringify(args));
        }
    }
}


/** 
 * let callCount = 0;
 * const memoizedFn = memoize(function (a, b) {
 *	 callCount += 1;
 *   return a + b;
 * })
 * memoizedFn(2, 3) // 5
 * memoizedFn(2, 3) // 5
 * console.log(callCount) // 1 
 */
```

### 12]. 2723. Add Two Promises

**Given two promises promise1 and promise2, return a new promise. promise1 and promise2 will both resolve with a number. The returned promise should resolve with the sum of the two numbers.**

```
var addTwoPromises = async function (promise1, promise2) {
    const [value1, value2] = await Promise.all([promise1, promise2]);
    return value1 + value2;
};
```

### 13]. 2621. Sleep:

**Given a positive integer millis, write an asynchronous function that sleeps for millis milliseconds. It can resolve any value.**

```
/**
 * @param {number} millis
 */
async function sleep(millis) {
    await new Promise(resolve => setTimeout(resolve, millis));
}

/** 
 * let t = Date.now()
 * sleep(100).then(() => console.log(Date.now() - t)) // 100
 */
```

### [14]. 2715. Timeout Cancellation:

**Given a function fn, an array of arguments args, and a timeout t in milliseconds, return a cancel function cancelFn.
After a delay of cancelTimeMs, the returned cancel function cancelFn will be invoked.
setTimeout(cancelFn, cancelTimeMs)
Initially, the execution of the function fn should be delayed by t milliseconds.
If, before the delay of t milliseconds, the function cancelFn is invoked, it should cancel the delayed execution of fn. Otherwise, if cancelFn is not invoked within the specified delay t, fn should be executed with the provided args as arguments.**

```
/**
 * @param {Function} fn
 * @param {Array} args
 * @param {number} t
 * @return {Function}
 */
const cancellable = function(fn, args, t) {
     const cancelFn = function (){
      clearTimeout(timer);
  };
  const timer = setTimeout(()=>{
      fn(...args)
  }, t);
  return cancelFn ;
};
```
### [15]. 2725. Interval Calculation

**Given a function fn, an array of arguments args, and an interval time t, return a cancel function cancelFn.
After a delay of cancelTimeMs, the returned cancel function cancelFn will be invoked.
setTimeout(cancelFn, cancelTimeMs)
The function fn should be called with args immediately and then called again every t milliseconds until cancelFn is called at cancelTimeMs ms.**

```
/**
 * @param {Function} fn
 * @param {Array} args
 * @param {number} t
 * @return {Function}
 */
var cancellable = function(fn, args, t) {
     fn(...args);
    let timer = setInterval(() => fn(...args), t);

    let cancelFn = () => clearInterval(timer);
    return cancelFn;
};
```

### [15]. 2727. Is Object Empty:

**Given an object or an array, return if it is empty.
An empty object contains no key-value pairs.
An empty array contains no elements.
You may assume the object or array is the output of JSON.parse.**

```
/**
 * @param {Object|Array} obj
 * @return {boolean}
 */
var isEmpty = function(obj) {
    if (typeof obj === 'object' && obj !== null) {
        if (Array.isArray(obj)) {
            return obj.length === 0;
        }
        return Object.keys(obj).length === 0;
    }
    return false;
};
```
### [16]. 2677. Chunk Array:

**Given an array arr and a chunk size size, return a chunked array.
A chunked array contains the original elements in arr, but consists of subarrays each of length size. The length of the last subarray may be less than size if arr.length is not evenly divisible by size.
You may assume the array is the output of JSON.parse. In other words, it is valid JSON.
Please solve it without using lodash's _.chunk function.**

```
/**
 * @param {Array} arr
 * @param {number} size
 * @return {Array}
 */
var chunk = function(arr, size) {
  const chunkedArray = [];

  for (let i = 0; i < arr.length; i += size) {
    chunkedArray.push(arr.slice(i, i + size));
  }

  return chunkedArray;
};
```
