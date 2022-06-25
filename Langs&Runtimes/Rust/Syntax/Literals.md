### Intro
	In rust, a literal is an expression consisting of a single token instead of sequence. It imediately and directly denotes the value it evaluates. Literals are evaluated at compile time.

### Specifications
Literals may have the following formats and share with common formats the following escapes:
##### ASCII
- ``\n`` newline
- ``\x41`` 7-bit character (exactly 2-digits, up to 0x7F)
- ``\r`` carriage return 
- ``\t`` tab
- ``\\`` backslash
- ``\0`` null
##### Byte
- ``\x7F`` 8-bit character (exactly 2-digits)
- same others as ASCII excluding ``\x41`` 
##### Unicode
- ``\u{7FFF}`` 24-bit Unicode character (up to 6 digits)
##### Quotes
- ``\'`` single
- ``\"`` double
##### Numbers
- Decimal integers
- Hex integer
- Octal integer
- Binary Integer
- Floating-point

	**Info all number literals accept ``_`` as a visual separator, e.g.: ``1_234`` -> 1234**

##### Suffixes
In rust macros accept suffixes, it is then decided by the macro itself if this should result in an error or success. 
Suffices are positioned directly after the end of any string, integer, etc, e.g.: 
```rust
	potato!("string"suffix)
```
However, suffixes on literal tokens are rejected on non-numeric literal tokens and numeric literal tokens are accepted only with the following suffixes:
	``u8``,  ``i8``, ``u16``, ``i16``, ``u32``, ``i32``, ``u64``, ``i64``, ``u128``, ``i128``, ``usize``, ``isize`` 
And their float point should be at: 
	``f32``, ``f64``

### Char and string literals




