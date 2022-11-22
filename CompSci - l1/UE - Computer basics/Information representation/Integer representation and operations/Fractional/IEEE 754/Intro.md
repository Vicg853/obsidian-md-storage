The IEEE 754 standard, is a normalization of the floating point number representation, which is used until nowadays, for fractional number representation on computers.

The IEEE defined two representations for floating point numbers: a _32-bit called single precision_ and the _64-bit called double precision_, as it is more precise than its 32-bit brother, as its mantissa is larger. 

Just like any floating point number, you have the mantissa and the exponent, but the IEEE 754 also features a reserved sign bit, which means, the mantissa will always positive.
Additionally, the exponent is also always positive, as we add into it (for example, ``127`` with 32 bits), which allows faster comparison of exponent sizes (lexical binary order).

The order also applies a certain order: ``sign bit`` | ``exponent`` | ``mantissa``

#### Precision

|       |      Mantissa |Exponent|
|-------|-------------------|----|
|64-bit | 23 (+1 not stored)| 8  | 
|32-bit | 52 (+1 not stored)| 11 |
|128-bit|122 (+1 not stored)| 15 |