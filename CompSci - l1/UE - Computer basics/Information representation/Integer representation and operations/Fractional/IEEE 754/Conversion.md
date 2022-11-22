The methods to convert from binary to denary and vise versa.

#### To denary
First, the negative or positive sign, must be put inside the sign bit (1 for negative and 0 for positive).

We than convert the number into binary, to place it into the mantissa. The best way to do it, is creating a table, split in half by the decimal dot: values on the left are positive powers of 2 and to the right we have negative powers of two.
We then fill it with 1s and 0s based on our number. 
> [!TIP] Finding whole number
> To find the whole number we can use Euclid's algorithm, while always retaining the remainder, which together correspond to the respective whole value in binary.
> The sequence of bits, should be read from bottom to top (if you follow the downwards order of the Euclidian algorithm)

> [!TIP] Finding decimal part
> To find the decimal part, we the Euclid's algorithm inverse: we multiply by two, then keeping only the decimal part for the next step (if the result is``1.25`` we use only ``0.25`` for the next step) and retain the whole part of the result as the binary grouping for the decimal number part.
> The bits are now organized from top to bottom 

Finally we normalize the number (which will always correspond to a positive normalization as the mantissa is always positive) as seen [[Normalization#Positive normalization|here]] and we remove the first bit value as it will always be equals to one.
We keep track of the moves made, as this corresponds to the exponent level.

As our exponent is positive, we add $2^{\ \mathsf{(exp\ bit\ length)}\ -\ 1} - 1$ (where ``max`` is the maximum representable values for the respective exponent bit length), we then convert our denary exponent into binary.

#### From denary
First, we determine the sign.

We convert the exponent into a  denary value and remove the bias (exponent minus $2^{\ \mathsf{(exp\ bit\ length)}\ -\ 1} - 1$).

We then convert the mantissa into denary.
> [!NOTE] Remember that the value was normalized, which means that the first bit of the mantissa corresponds to $2^{-1}$, the second to $2^{-2}$ and so on...

We add the whole one which was removed from the mantissa at encoding and finally calculate the scientific notation of this number ($\mathsf{mantissa} \cdot 2^{e}$ ) to retrieve our result.