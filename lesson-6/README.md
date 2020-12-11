# Functions

Functions are some of the most fundamental components of programming.

The very basics of a function are:

- You input some values
- It does something with those values
- Sometimes it returns a value

Let's say we wanted to add 2 numbers, `4` and `10`, we could do any of the following :

```js
const result = 4 + 10;
```

```js
const a = 4;
const b = 10;
const result = a + b;
```

```js
const a = 4;
const result = a + 10;
```

This should be relatively simple and the value of `result` will be `14` in all cases.

However, we can also use a `function` to do this.

```js
function sum(a, b) {
    return a + b;
}
```

The function above may look scary, but I promise you **will** make sense of it.

first we have:

`function sum`

This is the name of the function, then we have:

`(a, b)`

These are the `arguments` or paramaters. These are values that you will pass in.

`return a + b;`

This line means, whatever values `a`, `b` you pass in, it will `add` those values and `return` it. Returning something means that value is passed to whatever the function is assigned to, here's an example:

```js
function sum(a, b) {
    return a + b;
}

const value = sum(10, 20);

console.log(value);
```

```
$ node example.js
30
```

So, what's happened here is:

1. We've created a `function` that takes 2 `arguments`.
2. The function will then add those 2 `arguments` and `return` the value.
3. We're creating a `variable`, `value` that is equal to the `return` value of `sum(10, 20)`, which is `30`.
