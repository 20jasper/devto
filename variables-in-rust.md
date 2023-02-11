# Variables in Rust - Rust for TypeScript Developers

- [Variables in Rust - Rust for TypeScript Developers](#variables-in-rust---rust-for-typescript-developers)
	- [Initialization](#initialization)
	- [Scope](#scope)
	- [Reassignment](#reassignment)
	- [Redeclaration](#redeclaration)
	- [Mutability](#mutability)
	- [Hoisting](#hoisting)

## Initialization
In TypeScript, the initialization of variables declared with var is hoisted

```ts
console.log(x); // undefined
var x = 12;
console.log(x); // 12
```

The initialization of variables declared with let or const is not hoisted

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

Rust takes the more modern behavior of let and const and takes it one step further. Variables are not initialized unless they are assigned a value

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


## Scope
Variables declared with const in rust can be global, but variables declared with let cannot

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

In TypeScript, variables can be declared anywhere as long a

```ts
let x = 12;
const Y = 12;
```

## Reassignment
let mut allows in rust
js let/var allows
## Redeclaration
let in rust
var in js
## Mutability
rust everything is immutable without mut
it's by type in js


## Hoisting