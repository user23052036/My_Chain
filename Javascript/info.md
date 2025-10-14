
ctrl + shift + v for viewing markdown .MD pages

---

### 🧠 1️⃣ **Why we stopped using `var` and started adopting `let` (and `const`)**

`var` was part of **the original JavaScript (ES3 and before)**, but it had several **problems** that made code hard to debug and reason about.
So, in **ES6 (2015)**, two new ways to declare variables were introduced — `let` and `const`.

| Feature           | `var`                                | `let`                                              | `const`             |
| ----------------- | ------------------------------------ | -------------------------------------------------- | ------------------- |
| **Scope**         | Function-scoped                      | Block-scoped                                       | Block-scoped        |
| **Hoisting**      | Yes (but initialized as `undefined`) | Yes (but *not* initialized — “Temporal Dead Zone”) | Yes (same as `let`) |
| **Redeclaration** | Allowed in same scope                | ❌ Not allowed                                      | ❌ Not allowed       |
| **Reassignment**  | ✅ Allowed                            | ✅ Allowed                                          | ❌ Not allowed       |

#### 🚫 Problem with `var`:

```js
if (true) 
{
  var x = 10;
}
console.log(x); // 10 (still accessible outside the block!)
```

The variable `x` leaked outside the block — unexpected behavior.

#### ✅ Using `let`:

```js
if (true)
{
  let y = 10;
}
console.log(y); // ❌ Error: y is not defined
```

So `let` respects **block scope**, just like in most other programming languages (C++, Java, etc).

---

### 👨‍💻 2️⃣ **Who created JavaScript?**

**Brendan Eich** created JavaScript in **1995** while working at **Netscape Communications**.

* He built the **first version in just 10 days**.
* Originally called **Mocha**, then **LiveScript**, and finally renamed to **JavaScript** for marketing reasons.

---

### 💡 3️⃣ **Why was JavaScript created?**

At that time, web browsers could only display **static HTML** pages.
Eich’s goal was to make the browser **interactive** — e.g. validate forms, react to user input, etc.

So JavaScript was designed to:

* Run **inside browsers**
* Be **lightweight** and **easy to learn**
* Let designers and non-programmers add **logic** to web pages

---

### ☕ 4️⃣ **Why is it called “JavaScript”?**

It actually has **nothing to do with Java** in design or behavior 😄.

In 1995:

* **Java** (by Sun Microsystems) was extremely popular and hyped.
* Netscape partnered with Sun, and renamed “LiveScript” to “JavaScript” for **marketing appeal**.

So the name “JavaScript” was mainly **a marketing trick** — to ride on Java’s fame.

---

## 🧩 **`null` vs `undefined` in JavaScript**

| Concept           | `undefined`                                                                                   | `null`                                                                                           |
| ----------------- | --------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| **Meaning**       | A variable **has been declared but not assigned** a value.                                    | A variable is **explicitly assigned** to have **no value**.                                      |
| **Type**          | `undefined` (its own primitive type)                                                          | `object` *(this is actually a bug in JS from 1995!)*                                             |
| **Who sets it**   | **JavaScript itself** sets variables to `undefined` when they are declared but uninitialized. | **You (the developer)** set a variable to `null` when you want to explicitly say “nothing here”. |
| **Default value** | Default value of uninitialized variables, missing parameters, or missing object properties.   | Used to intentionally clear or reset a variable or object reference.                             |
| **Use case**      | When something *has not been defined yet*.                                                    | When something *is intentionally empty*.                                                         |
| **Example**       | `let a; console.log(a); // undefined`                                                         | `let a = null; console.log(a); // null`                                                          |

---

Perfect — here’s how you can **explain it confidently in an interview** 👇

---

### 💬 **Sample Interview Answer**

> In JavaScript, `typeof null` returns `"object"`, which is actually a well-known historical bug.
>
> When JavaScript was first implemented in 1995, values were stored as a combination of “type tags” and actual data in memory.
>
> The type tag for **objects was 0**, and `null` was represented as **all zero bits (0000)**.
>
> So when the `typeof` operator checked `null`, it saw the zero bits and mistakenly identified it as an object.
>
> This behavior has been part of JavaScript since its early versions, and **it can’t be fixed now because it would break a lot of existing code** that depends on it.
>
> So we just treat it as a quirk of the language — something developers need to be aware of.

---

### ⚙️ **If the interviewer asks for the fix:**

> The correct way to check for `null` is:
>
> ```js
> value === null
> ```
>
> or to check for both `null` and `undefined`:
>
> ```js
> value == null
> ```

---
Excellent question — this is one of the best ways to understand the **evolution of blockchain technology** as a whole.
Let’s build a clear **timeline of Bitcoin and its major forks and independent offshoots**, showing how the ecosystem branched and evolved from **2008 → today**.

---

## 🧠 **JavaScript Data Types**

JavaScript has **two categories** of data types:

### 🔹 1. **Primitive Data Types**

Primitive types are **immutable** and stored **by value**.

| Type          | Description                                               | Example                                      |
| ------------- | --------------------------------------------------------- | -------------------------------------------- |
| **Number**    | Represents both integer and floating numbers.             | `let x = 10; let y = 3.14;`                  |
| **BigInt**    | For very large integers beyond `Number.MAX_SAFE_INTEGER`. | `let big = 123456789012345678901234567890n;` |
| **String**    | Textual data enclosed in `' '`, `" "`, or `` ` ` ``.      | `let name = "Souvik";`                       |
| **Boolean**   | Represents `true` or `false`.                             | `let isValid = true;`                        |
| **Undefined** | A variable declared but not assigned a value.             | `let x;`                                     |
| **Null**      | Represents an intentional empty or "nothing" value.       | `let y = null;`                              |
| **Symbol**    | Used to create unique identifiers (ES6).                  | `let sym = Symbol("id");`                    |

---

### 🔹 2. **Non-Primitive (Reference) Data Types**

Stored **by reference** (not by value).

| Type                                                                            | Description                    | Example                                   |
| ------------------------------------------------------------------------------- | ------------------------------ | ----------------------------------------- |
| **Object**                                                                      | Collection of key-value pairs. | `let person = {name: "Souvik", age: 20};` |
| **Array**                                                                       | Ordered list of values.        | `let arr = [1, 2, 3];`                    |
| **Function**                                                                    | A callable object.             | `function greet() { console.log("Hi"); }` |
| **Date**, **RegExp**, **Map**, **Set**, etc. are special built-in object types. |                                |                                           |

---

## 📜 **ECMA (ECMAScript) Standard**

### 🔹 What is ECMA?

* **ECMA** = *European Computer Manufacturers Association*
* It defines **ECMAScript (ES)** — the **official standard** that JavaScript follows.

JavaScript = Implementation of ECMAScript.

---

### 🔹 Important ECMAScript Versions

| Version                   | Year      | Major Features                                                                  |
| ------------------------- | --------- | ------------------------------------------------------------------------------- |
| **ES3**                   | 1999      | First widely supported version.                                                 |
| **ES5**                   | 2009      | `"use strict"`, JSON, array methods like `forEach()`, `map()`.                  |
| **ES6 (ES2015)**          | 2015      | `let`, `const`, arrow functions, classes, modules, promises, template literals. |
| **ES7 (ES2016)**          | 2016      | `Array.includes()`, exponentiation `**` operator.                               |
| **ES8 (ES2017)**          | 2017      | `async/await`, object methods like `Object.entries()`.                          |
| **ES9 (ES2018)**          | 2018      | Rest/spread in objects, async iteration.                                        |
| **ES10 (ES2019)**         | 2019      | `flat()`, `flatMap()`, `Object.fromEntries()`.                                  |
| **ES11 (ES2020)**         | 2020      | Optional chaining `?.`, nullish coalescing `??`, BigInt.                        |
| **ES12 (ES2021)**         | 2021      | Logical assignment, `String.replaceAll()`.                                      |
| **ES13–ES15 (2022–2024)** | 2022–2024 | Top-level await, class fields, new array methods, etc.                          |

---

### 🔹 In Short:

* **ECMAScript** = the specification (rulebook).
* **JavaScript** = real-world implementation in browsers (Chrome, Firefox, Node.js, etc.).
* **New ES versions** = new JavaScript features standardized each year.

---
