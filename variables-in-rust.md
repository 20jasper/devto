# Variables in Rust - Rust for TypeScript Developers

- [Variables in Rust - Rust for TypeScript Developers](#variables-in-rust---rust-for-typescript-developers)
	- [Initialization](#initialization)
	- [Declaration](#declaration)
	- [Redeclaration](#redeclaration)
	- [Reassignment](#reassignment)
	- [Mutability](#mutability)

## Initialization
In TypeScript, the initialization of variables declared with `var` is hoisted

```ts
console.log(x); // undefined
var x = 12;
console.log(x); // 12
```

The initialization of variables declared with `let` or `const` is not hoisted

```ts
console.log(x);
let x = 12;
```
```
Uncaught ReferenceError: can't access lexical declaration 'x' before initialization
```
However, they are initialized with their declaration even if they aren't assigned a value

```ts
let x;
console.log(x) // undefined
```

Rust takes the more modern behavior of `let` and `const` and takes it one step further. Variables are not initialized unless they are assigned a value

This works
```rust
fn main() {
  let x = 12;
  println!("{x}"); // 12
}
```

This does not
```rust
fn main() {
  let x: i32;
    
  println!("{x}");
}
```
```
error[E0381]: used binding `x` isn't initialized
 --> src/main.rs:4:16
  |
2 |     let x: i32;
  |         - binding declared here but left uninitialized
3 |     
4 |     println!("{x}");
  |                ^ `x` used here but it isn't initialized
```

## Declaration
Variables declared with `const` in Rust can be global, but variables declared with `let` cannot

Note that variables defined with `const` must be explicitly typed

So this works,
```rust
const X: i32 = 12;

fn main() {
  
}
```

But this does not
```rust
let x = 12;

fn main() {
  
}
```

```
error: expected item, found keyword `let`
 --> src/main.rs:1:1
  |
1 | let x = 12;
  | ^^^ consider using `const` or `static` instead of `let` for global variables
```

In TypeScript, variables declared with `var`, `let`, or `const` can be declared anywhere and aren't required to be explicitly typed

```ts
let x = 12;
```

## Redeclaration
In TypeScript, variables assigned with `var` can be redeclared locally

```ts
var x = 12;
console.log(x); // 12

var x = 32;
console.log(x); // 32
```

Variables declared with `let` or `const` cannot be redeclared locally

```ts
const x = 12;
console.log(x);

const x = 32;
console.log(x);
```

```
Cannot redeclare block-scoped variable 'x'.
```

Rust's `const` works the same as TypeScript's in this sense

```rust
fn main() {
  const X: i32 = 12;
  const X: i32 = 12;
}
```
```
error[E0428]: the name `X` is defined multiple times
 --> src/main.rs:5:3
  |
4 |   const X: i32 = 12;
  |   ------------------ previous definition of the value `X` here
5 |   const X: i32 = 12;
  |   ^^^^^^^^^^^^^^^^^^ `X` redefined here
  |
  = note: `X` must be defined only once in the value namespace of this block
```

However, Rust's `let` works like `var` here—it can be redeclared in the same namespace 

```rust
fn main() {
  let x = 12;
  println!("{x}"); // 12
  
  let x = 43;
  println!("{x}"); // 43
}
```
## Reassignment
let mut allows in rust
js let/var allows
## Mutability
rust everything is immutable without mut
it's by type in js