# str and string

[ch08](https://doc.rust-lang.org/stable/book/ch08-02-strings.html#what-is-a-string)
> We’ll first define what we mean by the term string. Rust has only one string type in the core language, which is the string slice str that is usually seen in its borrowed form &str.
>
> The String type, which is provided by Rust’s standard library rather than coded into the core language, is a growable, mutable, owned, UTF-8 encoded string type. When Rustaceans refer to “strings” in Rust, they usually mean the String and the string slice &str types, not just one of those types. Although this section is largely about String, both types are used heavily in Rust’s standard library, and both String and string slices are UTF-8 encoded.

```rust
fn with_string(s: String) {
}

fn with_str(s: &str) {
}

fn main() {
    let s = "String";
    with_string(s.to_string());
    with_str(s);
}
```
