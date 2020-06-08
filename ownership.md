# Ownership

> Example #1 : Trace with Drop trait

```rust
#[derive(Debug)]
struct TestStruct;

impl Drop for TestStruct {
    fn drop(&mut self) {
        println!("=== GoodBye TestStruct ===");
    }
}

fn main() {
    println!("enter main");
    {
        println!("enter new scope");
        let x = TestStruct;
        println!("{:?}", x);
        println!("exit new scope");
    } // <-- x out of scope, dropped
    println!("exit main");
}
```
