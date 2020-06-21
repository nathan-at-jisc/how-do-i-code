# Objects

Without overcomplicating it too much, and `object` is an item that has `properties`. An example might be a car. The car is the `object`, but it also has `properties`. Some of these properties might be the colour, how many doors, make and model etc...

Here's how you write an `object`:

```js
const car = {
    make: 'ford',
    doors: 5,
    colour: 'grey'
}
```

Even though the syntax may not make sense, it should be evident that the `car object` has 3 `properties`: `make`, `doors` and `colour`, and these have respective values of `ford`, `5` and `grey`.

If we were to execute the follow code:

```js
const car = {
    make: 'ford',
    doors: 5,
    colour: 'grey'
}

console.log(car)
```

We would get

```
$ node example.js
{ make: 'ford', doors: 5, colour: 'grey' }
```

However, suppose we were only interested in the `colour` property, or even how many `doors` the car/`object` has. To get this information we can use the `dot notation`. We can simple do:

```js
const car = {
    make: 'ford',
    doors: 5,
    colour: 'grey'
}

console.log(car.colour)
console.log(car.doors)
```

Which would give us:

```js
$ node example.js
grey
5
```

Let's say we want to add a `property` to an existing object. In this example we might want to add the `age` of the car. To do this we can:

```js
const car = {
    make: 'ford',
    doors: 5,
    colour: 'grey'
}

console.log(car)

car.age = 10

console.log(car)
```

Which will give us:

```js
$ node example.js
{ make: 'ford', doors: 5, colour: 'grey' }
{ make: 'ford', doors: 5, colour: 'grey', age: 10 }
```