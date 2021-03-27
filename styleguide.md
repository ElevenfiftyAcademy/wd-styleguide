# EFA WD Styleguide

## JavaScript Language


### General Syntax

#### **Semicolons**

Semicolons are your choice but stick with said choice. Use them or don't; *consistency* is the important thing.

#### **Single vs. double quotes**

Like semicolons, choose one and stick to it.
***However***, note that specific contexts (like JSX) may have their own rules,
which should take precedence.

#### **Indentation**

Use two *or* four spaces. Note: **spaces**. I.e. not tabs. (VS Code should come configured for this already.)
Again, you must pick one (2 or 4) and be consistent.


#### **Brace positioning**

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

#### **Variables**






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
### Functions

#### **Fat arrow functions**









-------------------------------------------------------------------------------
## TypeScript

### Typing

#### **Interfaces vs. types**



***any* typing**