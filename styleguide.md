# EFA WD Styleguide

In this document you will find:
- mostly rules (❗ or ‼️),
- some rules that amount to "pick one option and be consistent" (⁉️), and
- a few suggestions (🔶).


## JavaScript Language


### General Syntax

#### **⁉️ Semicolons**

Semicolons are your choice but stick with said choice. Use them or don't; *consistency* is the important thing.


#### **⁉️ Single vs. double quotes**

Like semicolons, choose one and stick to it.
***However***, note that specific contexts (like JSX) may have their own rules,
which should take precedence.


#### **⁉️ Indentation**

Use two *or* four spaces. Note: **spaces**. I.e. not tabs. (VS Code should come configured for this already.)
Again, you must pick one (2 or 4) and be consistent.


#### **❗ Line length**

The traditional line length for most languages is 80 characters.
Although modern monitors often provide for more than this, 80 is a good default
especially in an environment when you will be sharing your screen and potentially enlarging your coding font.


#### **❗ Brace positioning**

As is the standard JavaScript practice, put the opening brace of a block of code
at the end of the line after which it starts.
You probably won't have problems with this unless you're coming from C# or another language where the other way is common.

```js
// no
if (x)
{
  ...
}

// yes
if (x) {
  ...
}
```


-------------------------------------------------------------------------------
### Naming Conventions


#### **Files**



#### **❗ Variable content**

Your variables should describe the content they hold.

```js
// no
let [x, y, z] = ["Toyota", "Corolla", 2008]

// yes
let [make, model, year] = ["Tesla", "Cybertruck", 2022]
```


#### **❗ Casing**

Variable names should be `camelCase`.

Exception: classes and React components should be `PascalCase`.

```js
// no
let var_one = 4
let VARTWO = 'banana'
class myClass {
  // ...
}

// yes
let varOne = 4
let varTwo = 'banana'
class MyClass {
  // ...
}
```


-------------------------------------------------------------------------------
### Semantics

#### **Triple equals**

Strict equality (===) over nonstrict (==).

```js
// no
if (x == '3') { ... }

// yes
if (x === '3') { ... }

// if you need to compare things, make sure they're the same type first
if (x.toString() === '3') { ... }
```

#### **Prefer const**

If you don't need to reassign a variable, you should use `const` to declare it.
You would be surprised how little you need to reassign variables.

#### **"If you use `var`, you won't get very far; try to use `let`, it's a much safer bet"**

Use `let` for mutable variables and `const` for constants (see previous).
`var` leads to confusion and should be avoided in pretty much all circumstances.



-------------------------------------------------------------------------------
### Conditionals



#### **Spacing**

`if`, space, condition, space, brace. The spaces are important.

Also, make sure `else` (or `else if`) statements are on the same line as the braces they are between.

```js
// no
if(x) {
  // ...
}
else {
  // ...
}

// yes
if (x) {
  // ...
} else {
  // ...
}
```



#### **Boolean equality comparisons**

Do not do unnecessary checks against a Boolean when you can just compare the value directly.

```js
if (x === true) { ... }
```


#### **Unnecessary ternaries**

Likewise, don't use a ternary where you can use a `||` operator.
This happens when the condition of the ternary is the same as the value you are returning in the positive case.

```js
// no
x ? x : 0

// yes
x || 0
```

-------------------------------------------------------------------------------
### Loops




-------------------------------------------------------------------------------
### Functions

#### **Anonymous ("fat-arrow") functions**








-------------------------------------------------------------------------------
-------------------------------------------------------------------------------
## TypeScript

### Typing

#### **Interfaces vs. types**

Prefer interfaces for object typing.
Type synonyms (i.e. what `type` introduces) can be pretty useful in certain cases,
all this rule says is to *prefer* interfaces when specifying object types unless you have a good reason
(say, an intersection type that's cleaner than `extend`ing an interface).


#### **`any` typing**

The `any` type should **only** be used on a first draft of your code,
as it essentially defeats the point of using TypeScript.
Always always always go back and provide a specific type for whatever you've marked as `any`,
or, better yet, build out the types correctly as you build everything else.
Students who neglect the TypeScript end up struggling later when they realize they need to add it,
and inevitably some of those `any`s never go away.




-------------------------------------------------------------------------------
-------------------------------------------------------------------------------
## React

#### **Component naming**

Components should be named with `PascalCase` (even if they are functions).

#### **To bind or not to bind**

Once you start learning legacy React, you'll have to make a decision as to whether to use the "bind" technique or to write methods as arrow functions attached to the class with property initializers. Again: make the decision and be consistent.

### Organization

#### **Nothing below `return` (a.k.a. don't foist the hoist)**

In a functional component, the `return` should be the last thing in the function.
This amounts to: don't rely on hoisting inside your functional components.

#### **Nothing below `render ()`**

Likewise, in a class component, the `render` method should be the last method in the class.
This isn't a hoisting thing as much as a general practice that helps with readability.