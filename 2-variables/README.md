## 2.1 Immutable Variables

- Declaration of variables by using keyword `let`
- By default variables in Rust are immutable
- Values are immutable(cannot be changed)

```rust
let x = 25;
println!("The value of x is: {}", x);
x = 75;
println!("The value of x is: {}", x);
```

```bash
error[E0384]: cannot assign twice to immutable variable `x`
 --> 2_1-immutable-variables.rs:4:5
  |
2 |     let x = 25;
  |         -
  |         |
  |         first assignment to `x`
  |         help: make this binding mutable: `mut x`
3 |     println!("The value of x is: {}", x);
4 |     x = 75;
  |     ^^^^^^ cannot assign twice to immutable variable
```


## 2.2 Mutable Variables

- Declaration of mutable variables by using keyword `let` followed by `mut`

```rust
let mut x = 25;
println!("The value of x is: {}", x);
x = 75;
println!("The value of x is: {}", x);
```


## 2.3 Variable Shadowing

- A variable can be shadowed by declaring a second variable with the same name as first
- The second variable must be declared with a `let` keyword

```rust
let x = 25;
println!("The value of x is: {}", x);
let x = 75;
println!("The value of x is: {}", x);
```

## 2.4 Difference between Shadowing and Mutable Variables

- For shadowing variable must be reassigned with keyword `let`
- Mutable variables must be reassigned with same datatype whereas in shadowing datatype can be changed

### Throws error when Mutable variable is reassigned with different datatype

```rust
let _text = "The quick brown fox jumps over the lazy dog.";
_text = _text.len();
```

```bash
error[E0308]: mismatched types
 --> 2_4-mutable-var-v-shawoding.rs:3:12
  |
3 |     text = text.len();
  |            ^^^^^^^^^^ expected &str, found usize
  |
  = note: expected type `&str`
             found type `usize`

error: aborting due to previous error
```

### No error when variable is shadowed

```rust
let _text = "The quick brown fox jumps over the lazy dog.";
let _text = _text.len();
```
