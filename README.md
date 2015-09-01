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
		return fibonacci(n - 1) + fibonacci(n - 2);
	}
}
```

## Script

[Rust][rust-lang] has some unique features. One way of getting to know these features is to explore familiar territory in a new light. In this excursion we explore a function to calculate the [Fibonacci][fibonacci] numbers. The Fibonacci numbers is a [sequence][A000045] starting with the numbers `0`, `1`, `1`, `2`, `3` where each new number is the sum of the preceding two numbers.

We will use the following naive implementation as a starting point to exploring [Rust][rust-lang].

[Rust][rust-lang] is an expression based language. This means that almost every syntactic structure returns a value. In this example we can forgo with all of the `return` keywords.

```rust
fn fibonacci(n: i32) -> i32 {
	if n == 0 {
		0
	} else if n == 1 {
		1
	} else {
		fibonacci(n - 1) + fibonacci(n - 2)
	}
}
```

Note that we also have to remove the semi-colon, otherwise [Rust][rust-lang] interprets this as an empty expression returning *unit*, which [Rust][rust-lang] catches as an incompatible types error

```rust
fibonacci(n - 1) + fibonacci(n - 2);
```

The convoluted `if-else-if-else` construction is at least not very readably or [Rust][rust-lang]-like. Better would be to use [Rust][rust-lang]s `match` keyword.

```rust
	match n {
		0 => 0,
		1 => 1,
		_ => fibonacci(n - 1) + fibonacci(n - 2)
	}
```

We could even collapse the two initial arms using a [`pattern`][pattern].

```rust
0...1 => n,
```

And there you have it, [Rust][rust-lang]-like fibonacci numbers


[rust-lang]: https://www.rust-lang.org
[fibonacci]: https://en.wikipedia.org/wiki/Fibonacci_number
[A000045]: https://oeis.org/A000045
[match]: https://doc.rust-lang.org/stable/book/match.html
[pattern]: https://doc.rust-lang.org/stable/book/patterns.html