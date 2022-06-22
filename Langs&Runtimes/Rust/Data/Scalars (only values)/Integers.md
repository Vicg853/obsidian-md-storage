Integers type in Rust.
|        **8-bit**            |   ``i8``      |   ``u8``      |
|:-----------------------:|:---------:|:---------:|
|        **16-bit**           |  ``i16``      |  ``u16``      |
| **32-bit<br>(default)**                 |  ``i32``      |  ``u32``      |
|        **64-bit**           |  ``i64``      |  ``u64``      |
|       **128-bit**           |  ``i128``     |  ``u128``     |
|       **sys arch**          | ``isize``     | ``usize``     |

- Types starting with ``i`` are signed integers: -1, -2, +3
- Types starting with u are un-signed integers: 1, 2, 3

In Rust integers can be represented as: 
- decimal (1,2, 3)
- hexadecimal ( ``0x1000``)
- octal (numbers represented in base8 format)
- binary (only for ``u8`` type)

What if literal overflow happens?
Well, in this case, there are two opposite results, for two different circumstances:
- At build time, Rust will simply, panic;
- For release builds, the value will be submitted to the called "complement wrapping", which means that the value will be wrapped to its minimum symmetric value, e.g. (we are considering our int is an ``u8`` in this case):
	- 256 -> 0;
	- 257 -> 1; ...