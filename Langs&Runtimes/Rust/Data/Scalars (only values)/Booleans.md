``true`` & ``false``. They are stored with an only byte, to either 1 or 0 respectively.

## Some operators
Logical comparisons: 
- not ``!b``
- or ``a | b``
- and ``a & b``
- xor ``a ^ b``
- comparison:
> `` a == b``
> ``a > b``
> ``a < b``
> ``a != b``
> ``a >= b``
> ``a <= b``

Lazy Operators: 
- Or ``let x = false || true;`` <- equals to true
- And ``let y = false && panic!();`` <- panic is not evaluated

#### Others
Other operators can be found at https://doc.rust-lang.org/stable/book/appendix-02-operators.html#operators.