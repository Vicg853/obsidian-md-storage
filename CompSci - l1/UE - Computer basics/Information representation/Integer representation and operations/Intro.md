We use a combination of bits to represent numbers in a computer. Each exact combination set, represents a single integer and this certain combination is defined by a convention, e.g.: 

|Binary|Decimal|
|--|--|
|0000|0|
|0001|1|
|0010|2|
|0011|3|
|...|...|

This convention follows the [[Base representation theory#Mathematical theory| base representation mathematical theory]]. Therefore the decimal representation of ``0011`` is justified by: 
$$0011 \iff 0 \cdot 2^3 + 0 \cdot 2^2 + 1 \cdot 2^1 + 1 \cdot 2^0 = 3$$ 

#### Bytes
We also need to define a rule, to be able to represent more complex numbers, as for exampe negative ones. The main one being a defined set of bits for each representation.

We therefore set the called "bytes" (octects in French), which constrains a groups of bits, that are always $2^N$ times bits. Therefore: 2 bits, 4bits, 8bits, 16bits, 32bits, 64bits, 128bits, 256bits, 512bits, 1024bits, 2048bits, 4096bit, ... (we could go on infinitely). 

With each higher power, our representation capacity also grows. It is useful noting that the representation capacity is also 
