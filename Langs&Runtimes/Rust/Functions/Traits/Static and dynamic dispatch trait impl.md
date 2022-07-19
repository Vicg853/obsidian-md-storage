In some cases, [trait bounds](../../Typing/Trait_bounds.md) with generics may be more than enough: the compiler creates an implementation for each case and uses them when respectively required. 

But sometimes, we may need more versatility, where a same implemented method must be genuinely used across multiple types and generics won't fit. That's when the called a dynamic dispatch, enters the scene.

When the compiler applies dynamic dispatch, instead of generating compile time variations, it figures out things at runtime. This can provide versatility while causing a slight runtime overhead.

#### Usage
To declare when a dynamic dispatch should be used, we use the ``dyn`` keyword, before trait implementation bound definition.
```rust
trait MyTrait {
	fn world(&self) {}
}

struct A {
	hello: Vec<Box<dyn MyTrait>>
}
```

> On the case above, now, elements passed to the ``A.hello`` struct, will be dynamically determined at runtime and the compiler will only an only ``A`` variation. When using the ``hello`` field in any way, its type will be determined at runtime.
> If we used generics instead, and a ``static`` implementation pattern, the ``A`` struct would probably be replicated as many times as required, preventing runtime check.

#### Rules
As usual, apart from "personal" decisions,  a set of rules will determine when each case must be used. The rules for static/dynamic dispatch implementations are called Object safety. 

When you are object safe, generics can be used. Object safe means:
- The implementation method's return type is not ``Self`` 
- The implementation method's parameters are not defined based of generics

If one of both rules can't be followed, the Rust compiler won't be able to define things at compile time and will require a runtime decision. 
