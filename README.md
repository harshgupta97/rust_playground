# Rust

Rust is statically typed language, which means that it must know the type of all variable at compile time.

## Rust common comands

### Manage installation

- Install
```
curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh
```

- Check versions
```
rustc --version
rustup --version
cargo --version
```

- Update rust and helpers

```
rustup update
```

- Get rust doc

```
rust doc
```

- Compile a rust code
```
rustc <file_name>
```

- Format rust file

NOTE: This will coding as well

```
rustfmt <file_name>
```

### Cargo

- Create new cargo

```
cargo new <project_name>
```

NOTE: Run command inside project

- Run cargo

Automatically build the code and run

```
cargo run
```

- Check code error before generating binary

```
cargo check
```

- Build cargo

```
cargo build
```

- Generate project document

```
cargo doc
```


### Common terms to remember

- trait - 

- Shadowing
    - let us use the variable name rather than forcing us to create two unique variable, such as guess and guess_string.
    - the second variable will overshadow the first, taking any use of the variable name to itself until either it itself is shadowed

INFORMATION: You cannot shadow a mutable let variable because a mutable variable will hold the data type information, but a variable which is not mutable can use shadowing because the second variable will use whatever it could from the first and then store it as a new one which means a different data type can use assigned to same variable but in case of mutable variable the second one will hold the same data type, it like we can assign the new value but of the same type.

- Ownership -

- panicking - when values is greater then the value an integer type can hold, panicking occures. LOOK integers section it will explain panicking more in details.

### Keywords

- match - like a switch statement, but only works with enum return by the methods
- loop - run the piece of code, untill told otherwise
- break - break out of the code
- continue - continue to run the code
- struct
- fn - function
- let - immutable variable will be created, variable can be converted into mutable by using "mut" keyword.
- const
    - Constants aren't just immutable by default they're always immutable.
    - constants may be set only to a constant expression, not the result of a value that could only be computed at runtime.

```
const THREE_HOURS_IN_SECONDS: u32 = 60 * 60 * 3;
```

- mut - muttable
- 

### Data types

#### Scaler Types

Scaler represent a single value;

- integers
    - use i in type
    - An integers is a number without a fractional component.
    - i is signed integer (can be both positive and negative)
    - u is unsigned integer (can be only positive)

    8-bit       i8      u8
    16-bit      i16     u16
    32-bit      i32     u32
    64-bit      i64     u64
    128-bit     i128    u128
    arch        isize   usize

    - signed number are stored using two's signed compliment.
    - isize and usize type depends on the architecture of the computer your program running on

INFORMATION: two's signed compliment - It is the most common method of representing signed(positive, negative and zero)

    - with --release flag, Rust does not includes checks for integer overflow that cause panics. Instead overflow occurs, Rust performs two's complement wrapping. In short, values greater than the value the type can holds "wrap around" to the minumum values the type can hold. In case of u8, the value 256 will become 0, 257 will become 1 and so on. The program won't panic, but the variable value will not be what we expect.

- floating-point
    - use f in type
    - Rust has two primitive types for floating-point numbers, which are number with decimal points
    - Rust floating point types are f32 f64, which are 32 and 64 bits in size respectively.
    - All floating-points types are signed
    - f32 are single-precision  float, and f64 has double precision.

- Numeric operation
```
fn main() {
    // addition
    let sum = 5 + 10;

    // subtraction
    let difference = 95.5 - 4.3;

    // multiplication
    let product = 4 * 30;

    // division
    let quotient = 56.7 / 32.2;
    let truncated = -5 / 3; // Results in -1

    // remainder
    let remainder = 43 % 5;
}
```

- Booleans
    - use bool in type
    - Boolean are one byte in size.

```
fn main() {
    let t = true;
    let t: bool = false; // with explicite type annotation
}
```
- Character
    - we specify char literals with single quotes, as opposed to string literals which use double.
    - Rust char type is four bytes in size and represent a Unicode Scalar Value. Which means it can represent a lot more than just ASCII. Accented letters; Chinese, Japanese, and Korean characters; emoji and zero width spaces are all valid char value in Rust.

INFORMATION: Unicode Scalar Value - Are the 21-bit codes that are the basic unit of Unicode. Each scaler value is represented by a unicode.

It ranges from U+0000 to U+D7FF and U+E000 to U+10FFFF


- Compund Types

Compound types can group multiple values into one type. Rust has two primitive compound types:

    - tuples
        - A tuple is general way of grouping together a number of values with a varity of types into one componend type. Tuples has fixed length once declared they cannot grow or shrink in size.

```
fn main() {
    let tup: (i32, f64, u8) = (500, 6.4, 1);

    // using destructuring
    let (x, y, z) = tup;

    // .follwed by index
    let five_hundred = x.0;

    println!("The value of y is {y}");
}
```
        - tuple without value is called unit.

    - arrays
        - unlike tuple, every element of an array must have the same type. Array in Rust have fixed length.

        - An array isn't as flexible as the vector type, though. A vector is a similar collection type provided by the standard library that allowed to grow or shrink in size.

```
fn main() {
    let array = [1, 2, 3, 4, 5];

    let array: [i32, 5] = [1, 2, 3, 4, 5];

    let initialized = [3; 5];

    let first = array[0];
    let second = array[1];
}
```

### Functions

Rust code uses snake case as the conventional style for function and variable names, in which all letter are lowercase and underscore seperate words.

```
fn main() {
    println!("Hello, World!");

    another_function();
}

fn another_function() {
    println!("Another function");
}
```

    - Statements - are instructions that perform some action and do not return a value;

    - Expression - evaluate to a resultant value. Let's look at some examples.

    


