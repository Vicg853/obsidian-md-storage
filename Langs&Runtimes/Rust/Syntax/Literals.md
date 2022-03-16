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
##### Character literal
`` ' ( ~[' \ \n \r \t ] | QUOTE_ESCAPE | ASCII_ESCAPE | UNICODE_ESCAPE ) ' ``
A character literal is a single Unicode character enclosed within two single quote characters

##### String
`` ' ( ~[" \ ``_IsolatedCR_`` ] | QUOTE_ESCAPE | ASCII_ESCAPE | UNICODE_ESCAPE | STRING_CONTINUE )* ' ``
A string iteral is a sequence of any Unicode characters enclosed within two double quotes

### Byte literals
- ``b" ( ASCII_FOR_STRING | BYTE_ESCAPE | STRING_CONTINUE ) "``
				_ASCII_FOR_STRING_: 0x00 to 0x7F, except for ``"``, ``\`` and _``IsolatedCR``_
- raw byte: ``br RAW_BYTE_STRING_CONTENT``
								_RAW_BYTE_STRING_CONTENT_: `"` ASCII* (non-greedy) `"`  | `#` RAW_BYTE_STRING_CONTENT `#`

### Integer literals
- Integer iteral: ``( DEC_LITERAL | BIN_LITERAL | OCT_LITERAL | HEX_LITERAL ) INTEGER_SUFFIX?``
- Decimal literal: DEC_DIGIT (DEC_DIGIT|`_`)*
- Binary iteral: ``0b`` (BIN_DIGIT|`_`)* BIN_DIGIT (BIN_DIGIT|`_`)*
- Oct literal: `0o` (OCT_DIGIT|`_`)* OCT_DIGIT (OCT_DIGIT|`_`)*
- Hexadecimal literal: `0x` (HEX_DIGIT|`_`)* HEX_DIGIT (HEX_DIGIT|`_`)*

##### Digits
- Binary digit: [0-1]
- Oct digit: [0-7]
- Decimal digit: [0-9]
- Hexadecimal digit: [0-9 a-f A-D]

##### Sufixes
	``u8``, ``u16``, ``u32``, ``u64``, ``u128``, ``usize``, ``i8``, ``i16`` | ``i32`` | ``i64`` | ``i128`` | ``isize``

### Tuples
- ``(``  [INT, STRING, ...] ``)`` 
- Tuple indexes: [TUPLE_IDENTIFIER]``.``[INDEX]
```rust
	let tupple = ("dog", "cat", "horse");
	let dog = tupple.0;
```

