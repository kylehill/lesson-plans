## JavaScript Control Flow

#### Equality Operators

`===` ("triple equals") compares two values without "type coercion". 

`==` ("double equals") compares two values while attempting type coercion.

```js
42 === "42" // false
42 == "42" // true
42 == "41" // false
```

`!==` and `!=` are the negative check for value equality comparison; `!==` does not attempt type coercion.

```js
42 !== "42" // true
42 != "42" // false
42 != "41" // true
```

`>` and `<` work as you'd expect for "greater than"/"less than".

`>=` and `<=` are the "greather than or equal to"/"less than or equal to" counterparts.

#### Truthiness

Yes, that's a real thing. Welcome to programming.

The following values are considered by JS to be **falsy**:

* `undefined`
* `""` (empty string)
* `0` (not string)
* `false`
* `null`
* `NaN` ("not a number", the result of most math errors)

**All other values are truthy.** 

Truthiness is relevant for a few things, but specifically for fulfilling or failing preconditions on code blocks.

#### Code Blocks

Important definition: A **code block** is any collection of statements that is bounded by curly braces - `{` and `}`. Code blocks can be nested inside of each other.

```js
{ 
  console.log("running me will just work"); 
  {
    console.log("me too!"); 
  }
}
```

There's no reason to do this unless you're attaching some precondition to the beginning of the code block.

#### If/Else

The most common precondition is `if`.

```js
var kylesAge = 31;

console.log("doing something before the block");

if (kylesAge > 21) {
  console.log("execute the code inside this block");
}

console.log("doing something after the block");
```

An `else` block can be added directly after an `if` block, which is executed *if and only if* the `if` condition is not met.

```js
var kylesAge = 31;

if (kylesAge > 21) {
  console.log("specials on happy hour");
}
else {
  console.log("i'm calling your parents");
}
```

`if` and `else` blocks can be nested. An `else` block only refers to the pass/failure of it's immediate matching `if`.

```js
if (thingIsTrue) {
    if (otherThingIsTrue) {
        console.log("so many true things");
    }
    else {
        console.log("okay one true thing");
    }
}
else {
    if (otherThingIsTrue) {
        console.log("a more different true thing");
    }
    else {
        console.log("like, zero true things");
    }
}
```

#### Loops

A `while` loop will execute a code block as long as a condition is truthy.

```js
var x = 0;

while (x < 5) {
  console.log("The value of x is " + x);
  x = x + 1;
}
```

Be aware -- the code block will execute over, and over, and over again forever if the precondition is not met.