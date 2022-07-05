Smart pointers in Rust are much like a mix of references and owned data in one: 
- they point to data in the memory just as references
- but at the same time, they have a higher overhead than references, as they own the data and carry some metadata about it (e.g.: you can create a smart pointer that keeps track of multiple data owners/references and that cleans that data when there are no more owners pointing to it)

There are actually two simple smart pointers in the Rust std library that are commonly used: ``String``s and vectors. 

Smart pointers are nothing more than a variation of structs, that implement both the deref and dropped traits.

Smart pointers can also be created from scratch, by the way, many libraries and frameworks implement their own smart pointers. Here we will cover just some of them, or at least the most important ones and the ones included on the STD library.

## Index
#### Traits
- The [deref trait](./Deref_trait)
- The [dropped trait](Drop_trait.md)

#### STD smart pointers
- The [Box](./Box) smart pointer


