# Function

> Example #1

```rust
// Both works, understand the differences!
fn with_array(_a: [&str; 3]) {// <- size
}

fn with_borrowed_str_array(_a: &[&str]) {// <- no size
}

fn main() {
    let a = ["one", "two", "three"];
    with_array(a);
    with_borrowed_str_array(&a);
}
```

> Example #2

```rust
// THIS DOES NOT WORK !
// *My Note* everybody shows you this does not work, but did not tell you how to make it work?!
// fn failed() -> &str {
//     let s = "string";
//     return s; <--| memory for s is deallocated which leads reference to invalid memory place. |
// }

// THIS WORKS
fn worked<'a>() -> &'a str {
    let s = "string";
    return s;
}

fn main() {
    let x = worked();
    println!("{}", x);
}
```

> Example #3
> Expand string value by passing mutable variable.

```rust
fn expand_x(y: &mut String) {
    y.push_str(" world");
}

fn main() {
    let mut x = String::from("hello");
    expand_x(&mut x);
    println!("{}", x);
}
```
