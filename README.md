# excursion-000
Where we visit Fibonacci in Rust style

## Setup
The following needs to be prepared

* A project named `fibonacci`
* Classic fibonacci code

```rust
fn main() {
    println!("fibonacci({}) = {}", 0, fibonacci(0));
    println!("fibonacci({}) = {}", 1, fibonacci(1));
    println!("fibonacci({}) = {}", 2, fibonacci(2));
    println!("fibonacci({}) = {}", 3, fibonacci(3));
    println!("fibonacci({}) = {}", 4, fibonacci(4));
    println!("fibonacci({}) = {}", 5, fibonacci(5));
    println!("fibonacci({}) = {}", 6, fibonacci(6));
    println!("fibonacci({}) = {}", 7, fibonacci(7));
}

fn fibonacci(n: i32) -> i32 {
	if n == 0 {
		return 0;
	} else if n == 1 {
		return 1;
	} else {
		return fibonacci(n - 1) + fibonacci(n -2);
	}
}
```