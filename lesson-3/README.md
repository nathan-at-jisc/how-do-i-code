# Arrays

Think of an `array` as a list. It's a variable that holds information and allows you to easily `sort`, `order`, `filter` and `map` that data. Let's say you have a shopping list, that shopping list might look like:

- Eggs
- Bread
- Milk
- Oranges
- Chips

If we were to write this as code, we could do it several ways:

```js
const shoppingList = ["Eggs", "Bread", "Milk", "Oranges", "Chips"]
```
Or we could make it more *readable*:

```js
const shoppingList = [
    "Eggs",
    "Bread",
    "Milk",
    "Oranges",
    "Chips"
]
```

You'll notice that all `items` in the `array` are seperated with a comma. You can now say that the 3rd item in the list/`array` is `Milk`, and you would be correct. However, `arrays` count from `0`, so in human form, our list might look like:

0. Eggs
1. Bread
2. Milk
3. Oranges
4. Chips

So let's say we wanted to `console.log` the 3rd item in the list, we could do it like this:

```js
const shoppingList = [
    "Eggs",
    "Bread",
    "Milk",
    "Oranges",
    "Chips"
]

console.log(shoppingList[2])
```

or:

```js
const shoppingList = [
    "Eggs",
    "Bread",
    "Milk",
    "Oranges",
    "Chips"
]

const thirdItem = shoppingList[2]

console.log(thirdItem)
```

The output would be the same:

```terminal
$ node example.js
Milk
```

The syntax for getting a certain item in a list/`array` is to put `[]` after the variable, and inside the `[]` the item number (keeping in mind it starts from 0).

So if we were to do:

```js
const shoppingList = [
    "Eggs",
    "Bread",
    "Milk",
    "Oranges",
    "Chips"
]

console.log(shoppingList[0])
console.log(shoppingList[1])
console.log(shoppingList[2])
console.log(shoppingList[3])
console.log(shoppingList[4])
```

We would get:

```terminal
$ node example.js
Eggs
Bread
Milk
Oranges
Chips
```

If we were to just do this:

```js
const shoppingList = [
    "Eggs",
    "Bread",
    "Milk",
    "Oranges",
    "Chips"
]

console.log(shoppingList)
```

We would get:

```
$ node example.js
[ 'Eggs', 'Bread', 'Milk', 'Oranges', 'Chips' ]
```

Another cool thing we can do is `sort` the `array`, and when an array contains `strings` (a string is just a word, a letter or a sentence), we can sort the `array` alaphabetically:

```js
const shoppingList = [
    "Eggs",
    "Bread",
    "Milk",
    "Oranges",
    "Chips"
]

console.log(shoppingList)

shoppingList.sort()

console.log(shoppingList)
```

Will give the following output:

```terminal
$ node example.js
[ 'Eggs', 'Bread', 'Milk', 'Oranges', 'Chips' ]
[ 'Bread', 'Chips', 'Eggs', 'Milk', 'Oranges' ]
```

Without going into to much detail, `.sort()` is `mutating` (this means to change an existing variable) and changing the oreder of the `shoppingList` variable. Notice how before we did `shoppingList.sort()`, the first `console.log` has the `array` in the original order, and after the `shoppingList.sort()`, the second `console.log` has it sorted alphabetically.

If we really wanted to, we could create some sentences from the `array`, we could add `I would like some x` instead of just performing a `console.log` of the `item`. There's a few ways we can do this:

```js
const shoppingList = [
    "Eggs",
    "Bread",
    "Milk",
    "Oranges",
    "Chips"
]

console.log("I would like some " + shoppingList[0])
console.log("I would like some " + shoppingList[1])
console.log("I would like some " + shoppingList[2])
console.log("I would like some " + shoppingList[3])
console.log("I would like some " + shoppingList[4])
```

You'll notice we're using a `+` symbol, when a variable isn't a `number`, it won't perform arithmetic, it will simply `add` the 2 values, this is refered to as `concatenation`. This output of the above code will be:

```terminal
$ node example.js
I would like some Eggs
I would like some Bread
I would like some Milk
I would like some Oranges
I would like some Chips
```

Which is hopefully what you would expect, as the following line is just adding `shoppingList[0]` to `I would like some `, and as we established earlier `shoppingList[0]` is the first element in the list/`array`, which in this case is `Eggs`.

```js
console.log("I would like some " + shoppingList[0])
```

## `for loops`

Outputing each item to the terminal line by line is very slow, and also flawed. In the example above, we have an `array` of 5 `items`. If were were to add an `item` the `array` would now have 6 `items`.