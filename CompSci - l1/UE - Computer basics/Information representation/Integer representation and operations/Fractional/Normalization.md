There are technically many ways to represent floating point numbers, even in normal scientific notation. The idea of normalization, is to always position the dot, to the right of the most relevant number, which will:
- maximize precision
- omit ambiguity 
- and facilitate arithmetic operations, as computers don't need to convert to similar formatted numbers

Following the above techniques, should result in normalized results.

#### Negative normalization
Normalizing positive integers, consists of moving the dot to the right of the last left most 1.

#### Positive normalization
Normalizing negative integers, consists of moving the dot to the right of the left most 0.

#### Final
In both cases, we finish by moving all values to the left making the value followed by the dot the right most value. The last moved bits, are filled with 0s.
