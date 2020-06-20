# Logic

## `if/else` statements

Often in programming you want to perform an action based on information. An example of this might be if the user of a website is an administrator, you might want to show them different bits of information. Now, just doing an `if` statement is a massive over simplification of how authentication/authorization works, but the underlying logic is the same.

Take the following code, here we're checking wether the `user` variable is equal to `admin`, and if it is we are outputing some text to the terminal/console.

```js
const user = "admin"

if(user == "admin"){
    console.log("this person is an admin")
}
```

You will notice that in the `if` statement we have a bit of code:

```js
user == "admin"
```

This is the logic statement, and if that statement is `true` (statement refers to the bit in the bracket), then the block of code will run (the block of code is what lies between the curly braces, `{}`).

```js
if(statement){
    blockOfCodeToRun
}
```

So in the original example we are checking if `user` equals `admin`, and to do this we can use `==`. The reason we use `==` as opposed to `=` is because:

- `=` set a values
- `==` compares a value

If we run the original example:
```js
const user = "admin"

if(user == "admin"){
    console.log("this person is an admin")
}
```

We will get:

```terminal
$ node example.js
this person is an admin
```

However, if we change the code to be:
```js
const user = "not an admin"

if(user == "admin"){
    console.log("this person is an admin")
}
```

We will now get

```terminal
$ node example.js

```

... nothing. The program will only `console.log` if the criter is met. So maybe want to add an `else` statement. The code inside the `else` statement is what runs if the `if` statement is not `true`. For example:

```js
const user = "not an admin"

if(user == "admin"){
    console.log("this person is an admin")
}else{
    console.log("this person is not an admin")
}
```

What we're saying in that example is that

> If the `user` is equal to `admin` then output `this person is an admin` to the terminal. However, if the `user` is not equal to `admin` then output `this person is not an admin`.

So if we were now to run this code, we would get:
```terminal
$ node example.js
this person is not an admin
```

This logic statement can be applied to all sorts of different things. Maybe on a website there is age verification, and if the user is younger than 18 thye're kicked off. In our example we're just going to `console.log` something, whereas in reality you might redirect to the home page if they're not over 18, other wise let them though. Let's take this example:

```js
const userAge = 19

if(userAge > 18){
    console.log("You are older than 18, you may see this content!")
}else{
    console.log("I'm sorry, you are too young to see this")
}
```

Would output:

```terminal
$ node example.js
You are older than 18, you may see this content!
```

However, if we change the code to be:

```js
const userAge = 16

if(userAge > 18){
    console.log("You are older than 18, you may see this content!")
}else{
    console.log("I'm sorry, you are too young to see this")
}
```

The output would now be:

```terminal
$ node example.js
I'm sorry, you are too young to see this
```

But what if you wanted multiple logic statements. Let's say you want to check explicit values. Imagine you had a user role, and we display different information based on whether they're a student, tutor or other (which could include guest etc...). We could do this:

```js
const userRole = "tutor"

if(userRole == "tutor"){
    console.log("You're a tutor")
}else if(userRole == "student"){
    console.log("You're a student")
}else{
    console.log("You're not a tutor or a student!")
}
```

If we were to run that code, we'd get:

```terminal
$ node example.js
You're a tutor
```

If we changed `userRole` to `student`:

```js
const userRole = "student"

if(userRole == "tutor"){
    console.log("You're a tutor")
}else if(userRole == "student"){
    console.log("You're a student")
}else{
    console.log("You're not a tutor or a student!")
}
```

We'd now get:

```terminal
$ node example.js
You're a student
```

And if we changed `userRole` to `unknown`:

```js
const userRole = "unknown"

if(userRole == "tutor"){
    console.log("You're a tutor")
}else if(userRole == "student"){
    console.log("You're a student")
}else{
    console.log("You're not a tutor or a student!")
}
```

We'd now get:

```terminal
$ node example.js
You're not a tutor or a student!
```

## `switch` statements

Now, there is a better way of doing this when it comes to discrete values, and that's called a switch statement. We can rewrite the above code into a switch statement:

```js
const userRole = "unknown"

switch(userRole){
    case "tutor":
        console.log("You're a tutor")
        break
    case "student":
        console.log("You're a student")
        break
    default:
        console.log("You're not a tutor or a studen")
        break
}
```

That syntax might look a bit scary, or confusing. But it in this case, it does the exact same thing as the code above it with the `if`, `if else` and `else` logic. We can break it down line by line:

Here we're setting the variable `userRole` to the value `unknown`.
```js
const userRole = "unknown"
```

On this line, we're essentially saying, use the value of `userRole` and go through each of the `case` statements and see if it matches. 
```js
switch(userRole){
```

On the next lines, we have the `case` statement as well as a `break`. This block of code is basically saying:
> If `userRole` equals `tutor`, then perform the code below it, which in this case it will `console.log`.

Then there's also the `break` statement. This is to stop the switch statement, so it doesn't check any of the other `cases`. But in this case, `userTutor` does not equal `tutor` so this block of code is skipped.
```js
case "tutor":
    console.log("You're a tutor")
    break
```

Then we have the next `case` statement, which is checking to see if `userRole` is equal to `student`, which it isn't, so it skips this.
```js
case "student":
    console.log("You're a student")
    break
```

Finally, we have the `default` statement. This is like an `else` statement and basically says, if none of the others are true, then perform the code here. Which in this case, will run as `userRole` was neither `tutor` or `student`.

```js
default:
    console.log("You're not a tutor or a student")
    break
```

Again, if this seems a little confusing, that's fine. Re-read it if you need to, but this will become second nature eventually.