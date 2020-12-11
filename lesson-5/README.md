# Combining Objects and Arrays

So far we've learned about `arrays`, `objects` and `for loops`. Now let's see how we can combine them.

If we start with an `array` of `objects`, we may have something like:

```js
const cars = [
    {
        make: 'ford',
        doors: 5
    },
    {
        make: 'vauxhall',
        doors: 5
    },
    {
        make: 'ferrari',
        doors: 3
    }
];
```

This `array` can be thought of as a list, and each `object` can be an item in the list. So we're effectively saying that the first item on the list, `cars[0]`, is:

```js
const firstItem = cars[0];
console.log(firstItem);
```

```
$ node example.js
{ make: 'ford', doors: 5 }
```

If we wanted to loop through the list and `console.log` (print) each item, we could do:

```
for(let i = 0; i < cars.length; i++){
    console.log(cars[i]);
}
```

We would get:
```
$ node example.js
{ make: 'ford', doors: 5 }
{ make: 'vauxhall', doors: 5 }
{ make: 'ferrari', doors: 3 }

```

If we just wanted to print the `make`, we could do:

```
for(let i = 0; i < cars.length; i++){
    console.log(cars[i].make);
}
```

We would get:
```
$ node example.js
ford
vauxhall
ferrari
```

For now, this seems quite arbitrary to just `console.log` things, and to be honest, it is. However, in the future we may need to grab the `array` from some data, i.e a list in a spreadsheet, or from a website. When we grab that data, we may want to display it on a dashboard in a table view, eventually we'll get onto practical use cases.

Another way to `loop` through `arrays` is with the `forEach` keyword. I'm not going to spend too much time on this as I don't want to confuse you, but with arrays you can do this:

```js
cars.forEach((car) => {
    console.log(car);
    console.log(car.make)
});
```

Don't worry if that makes no sense to you, but that is (for all intents and purposes) the same as:

```js
for(let i = 0; i < cars.length; i++){
    console.log(cars[i]);
    console.log(cars[i].make);
}
```

It's just using a `function` and `callbacks`, terms that will eventually become second nature to you!