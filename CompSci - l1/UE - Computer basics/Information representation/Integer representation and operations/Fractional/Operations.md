Before this, check [[Floating points | floating point]] and [[Normalization | normalization]].

### Addition
Adding two floating point binary numbers, consist of adding up their mantissas together. 
But first, their exponent must be the same, therefore making the points position also the same.

The convention, is to make the smaller exponent the same as the biggest one. We than move the mantissa's point and normalize it. 

The addition's result has the same exponent as the two added numbers. 
Sometimes, the result may also need normalization to be properly stored.

#### Truncating errors
Sometimes, when converting a number's exponent, some important bits may be lost (more precisely, ``1`` bits ). 
This could then result in the called truncate error, where the addition gives a different result than expected, caused by missing space to keep all of the mantissa's content. 

Hopefully modern CPUs, usually work with big enough mantissas which makes truncate error's quite rare.

### Subtraction
Subtraction, is done in a similar way as addition, with the only difference being: we need to convert the number on the right of the equation, into a negative number. 

This is done by converting the normalized and leveled (put to the same exponent) mantissa, into a negative number using two's complement technique. 

We may then proceed by adding the two numbers. 