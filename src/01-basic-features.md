---
marp: true
title: 01. Basic Features
description: Basic rust features
author: Jonatan Ziegler
theme: uncover
class:
  - invert
math: mathjax
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

## 01. Basic Features
![bg left:40% w:80%](https://www.rustacean.net/assets/rustacean-orig-noshadow.svg)

---

### Table of Contents
1. Variables
1. Data Types
1. Control Flow
1. Functions
1. Structs and Enums
1. Pattern Matching
1. Install and Use
1. For Further Reading
---

### Hello World!
```rust
fn main() {
    let world = "World";
    println!("Hello {}!", world);
}
```

---

### Variables
```rust
let x = 5; // immutable!

let mut y = 10; // mutable
y = 0;

let z: i32 = -11; // type annotation optional
```

---

### Data Types
| Type | Description | Example Value |
|---|---|---|
|`bool`| | `true`|
|`i8` `i16` `i32` `i64` `i128` `isize` | signed integers| `-1` |
| `u8` ... `u128` `usize` |unsigned  | `10` |
| `f32`, `f64` |float, double | `1.23` |
|`char`| unicode codepoint| `'a'` `'🦀'` |

---

| Type | Description | Example Value |
|---|---|---|
|`[T, N]`| array of `T` of size `N` | `[1,2,3]` |
|`(T, U, ...)`| tuple | `(1, '🦀')` 
| `()` | unit (empty tuple): one possible value | `()` |
| `!` | never: zero possible values | - |

---
### Strings

1) string slice `&str` (pointer to some text, immutable)
    e.g. `"hello"`
2) string `String` (dynamically growing vector)
    e.g. `String::from("hello")`

<br/>

always valid UTF-8

---

### Control Flow
```rust
if condition {
    foo();
} else {
    bar();
}
```
```rust
loop {
    forever();
}
```
```rust
while condition {
    buz();
}
```

---

```rust
// ranges
let _ = 0..10; // 0,...,9 
let _ = 0..=10 // 0,...,10

for i in 0..10 {
    ten_times();
}
```

---
### Everything is a Expression
```rust
let max_a_b = if a > b {
    a
} else {
    b
};
```

---
### Functions
```rust
fn foo(a: bool, b: String) {
    // do sth.
}

fn square(input: i32) -> i32 {
    return input * input;
}
```

"automatic return"
```Rust
fn square(input: i32) -> i32 {
    input * input // no semicolon
}
```

---


### Structs ($\approx$ Classes)
```rust
struct Human {
    name: String,
    age: u8,
    size: f32,
    gender: Gender,
    home: Option<Address>
}
```

---
### Enums

```rust
enum Gender {
    Female,
    Male,
    Other(String)
}
```
```rust
let gender = Female;
let gender = Other("however you identify yourself".into())

// shaddows old variable `gender`
```

---
### Behaviour
```rust
impl Human {
    fn say_name(&self) {
        println(self.name);
    }

    fn grow(&mut self, increment: u8) {
        self.size += increment;
    }
}
```
also possible for enums

---
### Optional Values (`Option` Enum)
```Rust
// predefined by rust
// T can be any type
enum Option<T> {
    Some(T),
    None
}
```
replacement for null

---
### Pattern Matching


```rust
let (a, b) = (4, 5);
```


```rust
match variable {
    value_or_pattern_1 => foo(),
    alternative_value => bar(),
    _ => default_action(),
}
```

---
### Example

```Rust
impl Gender {
    fn print_gender(&self) {

        let gender = match (self.gender) {
            Female => "female",
            Male => "male",
            Other(description) => &description,
        };

        println!("I am {gender}.");
    }
}
```

---

### Matching in `if`, `while`

```rust
if let Some(address) = person1.adress {
    print_address(address);
}
```
also in `while` loops

---

### Install Rust

rustup (version manager)
https://www.rust-lang.org/tools/install

rust-analizer in VS-Code

---
### Cargo (package manager)
```bash
cargo new package-name # create new package
# or
cargo init # make current folder to package

cargo build # compile

cargo run # run package
```

---
### Dependencies

`Cargo.toml`:
```toml
[package]
name = "Test"
version = "0.1.0"
edition = "2021"


[dependencies]
example-package = "1.0"
```

---

### Recommended Resources
(online) books
https://doc.rust-lang.org/book/

https://doc.rust-lang.org/rust-by-example/index.html

interactive training (rustlings):
https://github.com/rust-lang/rustlings

documentation:
https://doc.rust-lang.org/std

---


### Homework
Try rustlings until *at least* quiz 1


1. Install see link
1. run `rustlings watch`
1. fix errors