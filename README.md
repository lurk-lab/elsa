## lurk-elsa

![lurk-rs](https://github.com/lurk-lab/lurk-rs/actions/workflows/ci.yml/badge.svg)
[![Current Version](https://img.shields.io/crates/v/lurk-elsa.svg)](https://crates.io/crates/lurk-elsa)
[![License: MIT/Apache-2.0](https://img.shields.io/crates/l/lurk-elsa.svg)](#license)

> [!IMPORTANT]
> This repo is a fork of https://github.com/Manishearth/elsa. It supports a crate release which only increment on the original is a sync variant of the `FrozenIndexMap` and `FrozenIndexSet` data structures, used in Lurk.
> This feature was PRed to upstream in https://github.com/Manishearth/elsa/pull/67 and this crate should become obsolete if it merges.

_🎵 Immutability never bothered me anyway 🎶_

This crate provides various "frozen" collections.

These are append-only collections where references to entries can be held on to even across insertions. This is safe because these collections only support storing data that's present behind some indirection -- i.e. `String`, `Vec<T>`, `Box<T>`, etc, and they only yield references to the data behind the allocation (`&str`, `&[T]`, and `&T` respectively)

The typical use case is having a global cache of strings or other data which the rest of the program borrows from.

### Running all examples

```bash
cargo test --examples --features indexmap
```
