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

You'll notice that all `items` in the `array` are separated with a comma. You can now say that the 3rd item in the list/`array` is `Milk`, and you would be correct. However, `arrays` count from `0`, so in human form, our list might look like:

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

```js
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

```js
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

Another cool thing we can do is `sort` the `array`, and when an array contains `strings` (a string is just a word, a letter or a sentence), we can sort the `array` alphabetically:

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

```js
$ node example.js
[ 'Eggs', 'Bread', 'Milk', 'Oranges', 'Chips' ]
[ 'Bread', 'Chips', 'Eggs', 'Milk', 'Oranges' ]
```

Without going into to much detail, `.sort()` is `mutating` (this means to change an existing variable) and changing the order of the `shoppingList` variable. Notice how before we did `shoppingList.sort()`, the first `console.log` has the `array` in the original order, and after the `shoppingList.sort()`, the second `console.log` has it sorted alphabetically.

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

```js
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

Outputting each item to the terminal line by line is very slow, and also flawed. In the example above, we have an `array` of 5 `items`. If were were to add an `item` the `array` would now have 6 `items`.

You can think of a `for loop` as a bit of code that runs for a certain amount of iterations:

```js
for(let i = 0; i < 3; i++){
    console.log(i)
}
```

This will output:

```js
$ node example.js
0
1
2
```

So even though you might not understand what the code means, you can accept that it has counted from `0` to `2` essentially. Let's break down the `for loop`. On the first line you have essentially 3 statements inside the brackets `()`.

```js
for(let i = 0; i < 3; i++){
```

These statements are:

- `let i = 0`
- `i < 3`
- `i++`

And each statement is seperated by a semi-colon, `;`. 

The first statement is saying `start i at 0`.

The second statement is saying `for as long as i is less than 3, continue the loop`.

And the third statement is saying `at the end of each loop increase the value of i by 1`.

So to break down the code, what's happening is:

- We're saying that `i` has a value of 0 to begin with.
- We're then checking to see if `i` is less than `3`.
- If `i` is less than `3` then the code within the curly brackets, `{}` will be run, which in this case is `console.log(i)`
- Now that the block of code has run, add `1` to `i` (also known as incrementing).
- Now the process repeats again, except now `i` has a value of `1`, which is still less than `3`, so the code executes.
- Eventually `i` will equal `3` and at that point it is no longer less than `3` which will mean the code in the curly braces `{}` will no longer run.

If this seems a little complicated, don't worry, it will become easier the more you do it.

Before we move on, there's a nice `property` that we can access on arrays that tells us how long they are. This is called `.length`. For example:

```js
const shoppingList = [
    "Eggs",
    "Bread",
    "Milk",
    "Oranges",
    "Chips"
]

console.log(shoppingList.length)
```

Will output:

```js
$ node example.js
5
```

So now that we know how to find out how many items are in an `array`, we can make a `loop` from our `shoppingList`, to do this we can turn:

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

Into:

```js
const shoppingList = [
    "Eggs",
    "Bread",
    "Milk",
    "Oranges",
    "Chips"
]

for(let i = 0; i < shoppingList.length; i++){
    console.log("I would like some " + shoppingList[i])
}
```

What this code is effectively saying

> For as long as `i` is less than `shoppingLists.length` (which in this case is `5`), execute the code block and increment `i` by 1 at the end.

So, in the first instance, `i` is 0, so the code that is executed is:

```js
console.log("I would like some " + shoppingList[i])
```

But because `i = 0`, the code is effectively:

```js
console.log("I would like some " + shoppingList[0])
```

When that loop has finished, `i` is incremented, so `i` now equals `1`, meaning the following code will execute:

```js
console.log("I would like some " + shoppingList[0])
```

This will continue up until `i` is `5`, because the condition is `i < shoppingList.length` (which is 5), then it will only execute the code when `i` is `0`, `1`, `2`, `3` and `4`.