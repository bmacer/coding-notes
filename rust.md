get documentation on all used libraries

    cargo doc --open

create a new vector and add to it

    let mut v: Vec<i32> = Vec::new();
    let mut v2 = vec![1, 2, 3];
    v2.push(4);

use multiple items from the same module...

    use std::{cmp::Ordering, io};

how do you catch-all with a match case?

    _ => (),

struct update syntax

    fn main() {
        let u1 = User {
            username: String::from("brandon"),
            active: true,
        };
        let u2 = User {
            username: String::from("anya"),
            ..u1
        };
        println!("u2 name: {}, u2 active: {}", u2.username, u2.active);
    }

struct User {
    username: String,
    active: bool,
}

create and copy a string

    let s1 = String::from("hello");
    let s2 = s1.clone();

for loops

    for number in (1..4).rev()
    for element in a.iter()
    
you can break with an expression

    break counter * 2;

ternary operator with let

    let number = if condition { 5 } else { 6 };

create loop

    loop {...}

get a random 8-bit number

    let r: u8 = rand::random();

checking greater/less/equal logic

    use std::cmp::Ordering;
    match guess.cmp(&correct) {
        Ordering::Less => println!("too low"),
        Ordering::Greater => println!("too high"),
        Ordering::Equal => println!("right on!"),
        }

why use shadowing?

    re-"let" a variable to change it but prevent future (non-letted) changes, also change types

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
random module

    use rand::Rng;
    let num = rand::thread_rng().gen_range(1, 101);

