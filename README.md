# vector3

[![Crates.io](https://img.shields.io/crates/v/vector3)](https://crates.io/crates/vector3)
[![Docs.rs](https://img.shields.io/docsrs/vector3)](https://docs.rs/vector3)
[![Crates.io Downloads](https://img.shields.io/crates/d/vector3)](https://crates.io/crates/vector3)
[![License](https://img.shields.io/crates/l/vector3)](./LICENSE)

A Rust library for working with 3D mathematical vectors.

## Features

- Create vectors from `f64` or `i32` components, or from a tuple
- Serialize and deserialize vectors to/from strings
- Arithmetic operators: `+`, `-`, `*` (scalar), `/` (scalar)
- Dot product, cross product
- Magnitude, normalization, distance
- Angle between vectors (radians and degrees)
- `PartialEq` with floating-point epsilon comparison

## Installation

```toml
[dependencies]
vector3 = "2.0.1"
```

Or with `cargo-edit`:

```sh
cargo add vector3
```

## Examples

```rust
use vector3::Vector3;

// Dot product
let a = Vector3::from_i32(1, 2, 3);
let b = Vector3::from_i32(1, 2, 3);
assert_eq!(a.dot(&b), 14.0);

// Cross product
let a = Vector3::from_i32(1, 2, 3);
let b = Vector3::from_i32(3, 2, 1);
assert_eq!(a.cross(&b), Vector3::from_i32(-4, 8, -4));

// Angle between vectors (degrees)
let a = Vector3::from_i32(1, 0, 0);
let b = Vector3::from_i32(0, 0, 1);
assert_eq!(a.angle_deg(&b), 90.0);

// Arithmetic operators
let a = Vector3::new(1.0, 2.0, 3.0);
let b = Vector3::new(4.0, 5.0, 6.0);
let sum = a + b;
let scaled = a * 2.0;

// Serialization / deserialization
let v = Vector3::new(1.0, 2.0, 3.0);
let s = v.to_string();                          // "(1, 2, 3)"
let v2 = Vector3::try_from(s).unwrap();
assert_eq!(v, v2);
```

## License

This project is licensed under the terms in [LICENSE](./LICENSE).
