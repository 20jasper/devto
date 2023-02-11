# Variables in Rust - Rust for TypeScript Developers

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

No such restriction in TypeScript

```ts
let x = 12;
// runs fine!
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

## Initialization
js Only var's initialization ia hoisted (as undefined)
let, var, const all initialized as undefined when declared js

rust no vars are initialized when declared

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
## Hoisting