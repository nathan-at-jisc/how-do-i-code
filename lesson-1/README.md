# Getting Started

## Variables

What is a variable? In its simplest form, a variable is something that holds a value. Take the following code:

```js
x = 10
```

Even with zero programming knowledge it is evident that the variable `x` has a value of `10`. Likewise, we could have:

```js
y = "Hello"
```

Here, the variable `y` has a value of `"Hello"`. Notice how the value is in quoatons mark, `""`. This is because it is a `literal` value. If we were to have:

```js
y = Hello
```

The code would be looking for another variable called `Hello`, which doesn't exist as we haven't created it. However, let's take this example:

```js
name = "Nathan"

x = name
```

There, we are saying that `name` is equal to `"Nathan"`. We are then saying that `x` is equal to `name`. This must surely mean that that `x` also equals `"Nathan"`.

In reality, we should be **declaring** our variables explicitly. We can do this with the `const` and `let` keyword. 

```js
a = 10

const b = 11

let c = 12
```

There we have assigned 3 values to 3 different variables. Again, even though you don't currently know what `const` and `let` mean, it should be clear that:

- `a` has a value of `10`
- `b` has a value of `11`
- `c` has a value of `12`

We'll go through the 3 different ways of setting a value. The first way allows a variable to be changed. That quite literally means the value can change throughout the code. In the example below, a has 4 different values, `10`, `11`, `12`, `13`. However, it can only ever be one of these values at any one time.

```js
a = 10
a = 11
a = 12
a = 13
```

If you were to `console.log` these values, which simply means to show some text in the terminal:

```js
a = 10
console.log(a)
a = 11
console.log(a)
a = 12
console.log(a)
a = 13
console.log(a)
```
we would get an ouput like this:
```unix
$ node example.js
10
11
12
13
```

Let's look at the second way of setting a variable, `const`. The `const` keyword means that the `value` cannot be changed (it's slightly more complicated than this, but it's fine to think of it this way for now). So let's say we have the following code:

```js
const a = 10
console.log(a)
a = 11
console.log(a)
```

We would get an output of:
```terminal
$ node example.js
10
/Users/test/example.js:3
a = 11
  ^

TypeError: Assignment to constant variable.
```

When we run the code, we get an error, `Assignment to constant variable`. This is saying that we have already declared `a` to be `10`, we cannot redeclare it to `11`.

The third way of declaring a variable is by using the `let` keyword. The `let` keyword allows you to change the value of a variable. If we run the code below;

```js
let a = 10
console.log(a)
a = 11
console.log(a)
```

We would get an output of:

```
$ node example.js
10
11
```

If this doesn't make sense, and you're thinking "Why would I ever need to redeclare", then don't worry, a lot of this will make more sense the more you look at it!

## Arithmetic

Let's say we wanted to add 2 numbers together, how would we do that? Well, we could do:

```js
const x = 10 + 10
```

This would give `x` a value of `20`. We could also do:

```js
const firstNumber = 10
const secondNumber = 20

const sum = firstNumber + secondNumber
```

This would give `sum` a value of `30`. We can prove this by running the following code:

```js
const firstNumber = 10
const secondNumber = 20

const sum = firstNumber + secondNumber
console.log(sum)
```

And we would get the following output:

```terminal
$ node example.js
30
```

However, there's more to arithmetic than addition, we can perform many actions, take this code for example:

```js
const a = 10 + 10
console.log(a)

const b = 100 - 20
console.log(b)

const c = 30 / 2
console.log(c)

const d = 10 * 7
console.log(d)

const e = 6 ** 2
console.log(e)
```

Which outputs:

```terminal
$ node example.js
20
80
15
70
36
```

Hopefully you can tell what's going on, but if not:

- `a` addition
- `b` subtraction
- `c` division
- `d` multiplication
- `e` to the power of (2 in this case)
