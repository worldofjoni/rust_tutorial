---
marp: true
title: 00. What is Rust?
description: General overview about the Rust programming language
author: Jonatan Ziegler
theme: uncover
class:
  - invert
style: |
  h1 {
    font-size: 5rem;
  }
  h2 {
    font-size: 3rem;
  }
  h3 {
    
  }
---

# Rust

![bg left 60% drop-shadow:0,5px,10px,rgba(255,255,255,.1)](https://github.com/rust-lang/rust-artwork/blob/master/logo/rust-logo-512x512.png?raw=true)
![width w:8em](https://www.rustacean.net/assets/rustacean-orig-noshadow.svg)

---

### What is Rust? 🦀

* compiled ⚙️ and staticly typed ✅
* memory safe 🛟
* systems programming 💾 up to web development 🌐
* good performance 🚅 but high comfort 🛋️
* superior error handeling 🚨
* modern tooling 🧰 and package manager 📦

<!--
- if it compiles, it works (reliable)
- without GC (fast) => ownership
-
- Zero cost abstractions
- Make invalid state unrepresentable
- Cargo, docs, ...
-->

---

### Most Loved Language 7 Years in a Row

![h:10em drop-shadow](../res/Screenshot%202023-05-07%20161335.png)
<small>according to the [Stack Overflow Developer Survey](https://survey.stackoverflow.co/2022/#section-most-loved-dreaded-and-wanted-programming-scripting-and-markup-languages)</small>

---

### Helpful Compiler

![h:11em drop-shadow](../res/Screenshot%202023-05-07%20165023.png)

---

### Functional but OO\*

```rust
struct Person {
  name: String,
  age: u32,
}


fn main() {
  let persons = vec![Person::new(), Person::new()];

  let age_sum: u32 = persons.iter().map(|&p| p.age).sum();
}
```

<small>\*depending on your definition</small>

---

### Rust as Web Backend 📡

<style scoped> table {font-size: 25px;} </style>

| Framework                        | Language                        | Speed                          |
| -------------------------------- | ------------------------------- | -------------------------------- |
| dragon-core                      | C++                             | 100.0%                             |
| <span style="color: lime">arctix | <span style="color: lime"> Rust | <span style="color: lime">83.1%  |
| <span style="color: lime">axum   | <span style="color: lime"> Rust | <span style="color: lime"> 80.9% |
| asp.net                          | C#                              | 63.9%                            |
| <span style="color: orangered">nodejs                           | <span style="color: orangered">JavaScript                      | <span style="color: orangered">13.0%                              |
| <span style="color: orangered">express                          | <span style="color: orangered">JavaScript                      | <span style="color: orangered">6.6%                             |
| spring                           | Java                            | 3.6%                             |
| laravel                          | PHP                             | 2.7%                             |
| django                           | Python                          | 2.4%                             |
| rails                            | Ruby                            | 1.6%                             |

<small>Quelle: https://www.techempower.com/benchmarks/</small>

---

### Rust is Different ...

- Ownership 🏠
- Lifetimes ⏳

<br/>

* ... and can sometimes be HARD 😖
<style scoped> ul {margin: 0; list-style-type: none; text-align: center} </style>
<!-- Thing you normally don't have to care about-->

---

![bg brightness:50%](../res/drew-beamer-xU5Mqq0Chck-unsplash.jpg)

## Rust is the Future!

used in Linux 🐧 and soon Windows 🪟 kernel
<br/>

* #### Rust 🦀 is Here to Stay!

<style scoped> ul {margin: 0; list-style-type: none; text-align: center} </style>
<!-- First language other than c Linus Torvalds approved-->
