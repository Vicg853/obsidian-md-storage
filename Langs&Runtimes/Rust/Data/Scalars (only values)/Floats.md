There are only two floating point types in Rust: ``f32`` and ``f64``. Both are _always_ stored as signed integers and Rust default's floating numbers to ``f64``, as it has roughly the same performance as ``i32`` on modern computers while being more precise.

Floating numbers in Rust comply to the IEEE 754-2008 regulation (single precision point for ``i32``s and double for ``i64``s).



