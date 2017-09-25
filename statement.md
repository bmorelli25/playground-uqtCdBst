# JavaScript: Why does 3 + true = 4?
JavaScript can be a *weird* langauge at times. In this article we'll explore 8 different equations that explain just a few of the JS quirks you should be aware of.
---

### 3 + true == 4
In JavaScript, when the plus operator is placed between a number and a boolean, the boolean is coerced (converted) into a number. With this in mind, run the code snipped below:

```javascript runnable
console.log(3 + true);
console.log(3 + false);
```

In the above code we add 3 to `true` and then 3 to `false`. Our answers are `4`, and `3`, respectively. What we can determine from this example is that JavaScript coerces a `true` boolean into the value of `1`, and a `false` boolean into the value of `2`. Let's set up an equality equation to test this theory:

```javascript runnable
console.log(true == 1);
console.log(flase == 1);
```

### Welcome!

This Node.js template lets you get started quickly with a simple one-page playground.

```javascript runnable
console.log('Hello World!');
```

# Advanced usage

If you want a more complex example (external libraries, viewers...), use the [Advanced Node.js template](https://tech.io/select-repo/442)
