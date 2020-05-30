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

```
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
