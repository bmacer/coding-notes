compile rust file

    rustc main.rs
create new project with cargo

    cargo new my_project
build with cargo [generates in ./target/debug/hello_cargo

    cargo build
build and run at once with cargo

    cargo run
check if compilable

    cargo check
build for release [generates in ./target/release/hello_cargo]

    cargo build --release
library to get user input

    use std::io;
declare a variable

    let mut guess = String::new();
get user input for guess

    io::stdin()
      .read_line(&mut guess)
      .expect("error reading line");
