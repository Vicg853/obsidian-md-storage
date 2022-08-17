## Integers type in Rust.
|        **8-bit**            |     ``i8``    |    ``u8``    |
|:---------------------------:|:------------:|:------------:|
|        **16-bit**           |    ``i16``    |   ``u16``    |
|   **32-bit<br>(default)**   |    ``i32``    |   ``u32``    |
|        **64-bit**           |    ``i64``    |   ``u64``    |
|       **128-bit**           |    ``i128``   |   ``u128``   |
|       **sys arch**          |   ``isize``   |   ``usize``   |

- Types starting with ``i`` are signed integers: -1, -2, +3
- Types starting with ``u`` are un-signed integers: 1, 2, 3

In Rust integers can be represented as: 
- decimal 
  > prefix none
  > Fun fact: you may use an ``_`` to highlight decimal integer separations, e.g.: ``1_000`` instead of ``1000``, which makes readability easier in most cases
- hexadecimal 
>   prefix ``0x``
- octal 
  > prefix ``0o``
- binary 
>   prefix ``0b``
- Bytes (_for u8 only!!_)
>  prefix ``b'`` - suffix ``'``

## Literal overflows
What if literal overflow happens? Well, in this case, there are two diferent possibilities and circumstances:
- At build time, Rust will simply, panic;
- For release builds, the value will be submitted to the called "complement wrapping", which means that the value will be wrapped to its minimum symmetric value, e.g. (we are considering our int is an ``u8`` in this case):
	- 256 -> 0;
	- 257 -> 1; ...

#### Manual handling
You may handle/check overflow cases manually. The ``std`` library introduces ``wrapping_*``, ``checked_*``, ``overflowing_*`` or ``saturating_*`` methods specifically for such occurrences.