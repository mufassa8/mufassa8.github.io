---
layout: post
title: Getting started **Rust**
---
link - https://www.youtube.com/watch?v=MddGbXgIt2E

### Base preparation
- make rust file(.rs)

- set basic package with `cargo`
    ```Bash
    cargo init
    ```
    > makes .toml(configuration, property file) and etc.

#### Rust, basic print options
- get function from outside of `main.rs`
    ```Rust
    mod print //the name of method to import
    ```
    > in Rust, default access modifier is `private` so if to import,  add prefix `pub` to designated function

    - example
        - `main.rs`
            ```Rust
            mod print;

            fn main() {
                print::run();
            }
            ```
        - `print.rs`
            ```Rust
            pub fn main() {
                println();
            }
            ```
### Web App with ***Yew*** (not finished)
- **Trunk** is that help us to build and package web assembly application.
    ```
    cargo install trunk
    ```

    ```
    rustup target add wasm32-unknown-unknown
    ```

- create new package (creating directory) and get into the directory
    ```
    cargo new RustFrontEnd
    cd RustFrontEnd
    ```

- add dependency in `.toml` file (ex. Cargo.toml)
    ```
    [package]
    name = "RustFrontEnd"
    version = "0.1.0"
    edition = "2021"

    # See more keys and their definitions at https://doc.rust-lang.org/cargo/reference/manifest.html

    [dependencies]
    yew = "^0.19" // <- add this
    ```

### Rust codes
#### main
- simple execute command
```
cargo run
```
- remove the template code

- bring everything(macros, functions) we need to build for web app
    ```
    use yew::prelude::*;
    ```