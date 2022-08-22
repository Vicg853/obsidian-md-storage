Ownership is the memory management model that Rust follows, providing your app with a safe memory environment with no garbage collector or leaks. 

This model works with three specific rules, that ensures these features:
1. Each value has a variable, called its owner
2. Each value always has one and only owner
3. When a value's owner goes out of scope, the same is dropped

Ownership ensures our program can safely allocate and deallocate memory (from the heap), without double freed, memory corruption, or dangling memory. But keep in mind, that ownership isn't totally applied in all types: push/pop variable types (which can be stored on the stack), are copied by default.

## Strings and som compound types
Strings are on of the most complicated types to manage and store in memory. They are usually either allocated on the heap or in the program's binary. What is kept on the stack, is actually a simple pointer to this data, which has a compile time know size.

Quoting the three rules: to keep ownership, we can only have an only pointer on the stack, pointin to allocated data, as having more than one, could result in double frees. 

So, in the example bellow, we are actually moving ``x`` to ``y``. Which means that ``x`` does not exist anymore after its pointer has been moved to ``y``. This also means that the underlying ``String`` data, is now owned by ``y``:
```rust
let x = String::from("Hello world!");
let y = x;
```

We could optionally clone ou ``String`` instead of moving it. Now we have two equal ``String`` values, both having its own only onwer and valid:
```rust
let x = String::from("Hello world!");
let y = x.clone();
```

> Note that, clone on compound types, can be pretty expensive, as performance wise. Our system needs to look for the data on the heap, talk with the allocator to allocate memory and then duplicate the data on the new opened space.

## Scalar values, the ``Drop`` trait and the ``Copy`` trait
Although most compound values must be either moved, or referenced or copied, and inflict quite some complexity, scalar types are pretty simple: they are simply copied by default.

Don't worry, copying scalars is fast as fuck, as they are stored on the stack, we simply push a copy of the data. Just like that: no search, or allocation requests. Moving or copying data to the stack, has almost no performance difference.

So when we do this, both ``x`` and ``y`` are valid, as our integer is simply being copied by default:
```rust 
let x = 5;
let y = x;
```

But how does Rust keeps track of all this? It uses the ``Drop`` and ``Copy`` traits. Every type that implements the ``Copy`` trait, is usually pushed to the stack, therefore it can be copied by default. 
While, every type that implements the ``Drop`` trait, is allocated to the heap and _can't_ implement the ``Copy`` trait. As they impl ``Drop``, they have a special way of deallocating memory, we can't simply pop it from the stack, we must call its ``drop()`` method, which does something special. 

Which types implement the ``Copy`` trait: 
- All Integers types
- All Floating point types
- All bolean types
- ``char`` types
- tuple types: _only if they are solely composed of  ``Copy`` implemented types_ (example: ``(i32, String)``s won't work, while ``(i32, i32)`` would work)

## Function and returns
The same applies when we call functions, types that implement ``Drop`` are moved, while the ones that implement ``Copy`` are simply duplicated.

And although functions may take ownership, we may also return ownership from it.

```rust 
fn take_and_give_back(my_string: String) -> String {
	my_string //This return hands over my_string's ownership back 
}

let my_string = String::from("A");
let x = take_and_give_back(my_string);

//Now my_string's previous value is onwed by x
//the take_and_give_back function, took ownership of our string
//and gave it back to x 

fn just_copy(my_int: u32) -> String {
	my_string
}

let my_int = 5;
just_copy(my_int)
let y = my_int; //This is valid, as my_int was simply copied by just_copy
```