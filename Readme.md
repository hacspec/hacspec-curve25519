# hacspec example - curve25519

This repository is a standalone hacspec example implementing curve25519.

The implementation is in [curve25519.rs](src/curve25519.rs) with tests in [test_curve25519.rs](tests/test_curve25519.rs).

### Dependencies
First ensure that Rust nightly and the typechecker are installed.

**NOTE:** This crate links against the main branch of the hacspec standard library on Github instead of the crates.io version.

**NOTE:** Installing `hacspec` currently requires to set the version to `--version 0.2.0-beta.1` because it's a pre-release version.

```bash
rustup toolchain install nightly
rustup component add --toolchain nightly rustc-dev
cargo +nightly install hacspec
```

### Typechecking

Typechecking can be done as follows now:

```bash
cargo +nightly hacspec hacspec-curve25519
```

Note that the crate needs to be compiled before it can be typechecked.

```bash
cargo +nightly build
```

If typechecking succeeds, it should show

```bash
> Successfully verified.
```

### Generating code
To generate F* or EasyCrypt code from hacspec the typechecker (see above) is required.

```bash
cargo +nightly hacspec -o Hacspec.Curve25519.fst hacspec-curve25519
cargo +nightly hacspec -o Hacspec_Curve25519.ec hacspec-curve25519
```