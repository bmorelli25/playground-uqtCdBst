# JavaScript: Why does 3 + true = 4?
JavaScript can be a *weird* langauge at times. In this article we'll explore 8 different equations that explain just a few of the JS quirks you should be aware of.
---

### Adding a Number to a Boolean
In JavaScript, when the plus operator is placed between a number and a boolean, the boolean is coerced (converted) into a number. With this in mind, run the code snipped below:

```javascript runnable
console.log(3 + true);
console.log(3 + false);
```

In the above code we add 3 to `true` and then 3 to `false`. Our answers are `4`, and `3`, respectively. What we can determine from this example is that JavaScript coerces a `true` boolean into the value of `1`, and a `false` boolean into the value of `2`. Let's set up an equality equation to test this theory:

```javascript runnable
console.log(true == 1);
console.log(false == 0);
```

We get true back for both equations. Now that we know the values that `true` and `false` coerce to, try answering this quiz question correctly:

?[What is 3 + true + true + false - true]
-[ ] 2
-[ ] 3
-[x] 4
-[ ] 5

### Adding A String to a Number
What happens when we add a string to an actual number? Run the code below and lets see if the answer is what you expect:

```javascript runnable
console.log('Number + Number:', 4 + 8);
console.log('String + Number:', "4" + 8);
```

 We get `48`? You see, when the plus operator is placed between to operands, and one is a string, it will convert the other number *or boolean* to a string and concatenate them. By this logic: `'4' + 8` becomes `'4' + '8'` and we get an answer of `'48'`.
 
 Let's try another example:
 
 ```javascript runnable
console.log("1" + 1 + 1);
```

Addition in JavaScript has left-to-right associativity. This means that when we have an equation with multiple `+` opperators, the left-most operator is evaluated first. Here's a visualization of what that would look like:

```
"1" + 1 + 1
  "11"  + 1
       "111"
```

But what happens if our string value is the last value in our equation? Would anything change? Run the following code and lets see. Notice that the difference between this example and the example above is the location of our string variable.

 ```javascript runnable
console.log(1 + 1 + "1");
```

`21`?! Yes! That's because order of operations is very important. In this instance, JavaScript evaluates the first + before anything else: `1 + 1` which equals `2`. Only then do we move on and add in the string value of `'1'`. Now String concatenation occurs and the result is `'21'`.

Here’s the chain of events:
```
1 + 1 + "1"
  2   + "1"
       "21"
```

Based on what we've learned so far, what do you think would happen here?

?[What is 25 + true + "2"]
-[ ] 28
-[ ] 252
-[x] 262
-[ ] 2512

### Using the negative operator
What if we attempt to negate a string with the negative operator and then add it to a number? For example, `-"50" + 50`. What would the answer be? Let's look at an example:

```javascript runnable
console.log('String + Number:', "50" + 50);
console.log('Negative + String + Number:', -"50" + 50);
```

As expected, our String + Number result is `"5050"` due to string concatenation. Howver, the negation in the second equation changes things. The minus sign before `"50"` is a unary minus operator that will actually **coerce** the string into a number and make it negative. Thus, our equation becomes `-50 + 50` which equals `0`.

Seeing as the minus operator coerced our string value into a number, what happens if we use the minus operator on a different value of string? Let's look at this example: `-"giddyup" + 409`. JavaScript is going to try to coerce our `"giddyup"` string into a number value. But will it be able to? Run the code below:

 ```javascript runnable
console.log(-"giddyup" + 409);
```

When JavaScript fails to coerce a number in the example above, we are left with NaN (Not A Number).

---

### Final Quiz
Now it's time to combine everything we've learned in this article and answer one final question. Are you up for it?

?[What is 25 + -"2" - false + "10"]
-[ ] 12
-[x] 2310
-[ ] 2710
-[ ] 252010

---

### You made it!
Good work! I hope you enjoyed my article. This article was originally published at [codeburst.io](https://codeburst.io/javascript-why-does-3-true-4-and-7-other-tricky-equations-9dd13cb2a92a)
