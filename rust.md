get documentation on all used libraries

    cargo doc --open
 
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
