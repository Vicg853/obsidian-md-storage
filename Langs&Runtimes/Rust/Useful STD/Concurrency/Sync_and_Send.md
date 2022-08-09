Although concurrency is not widely implement inside the Rust lang or std library, it still provides core utilities, for everything to work fearlessly. One of those core features, that provide this safety are the ``Sync`` and ``Send`` traits. 

Both traits are: unsafe, are implemented to most primitive types, shouldn't be required implemented anywhere else, apart from where it already has been defined (though you can do) and don't even require any methods to be implemented.

They should mostly be used as "markers" to ensure some thread safety characteristics on trait bounds and they don't shouldn't be necessary anywhere else because any type that only implements ``Sync`` or ``Send`` compilant types, will also be characterized as ``Sync`` or ``Send``.

## The ``Send`` trait
The ``Send`` trait, means a type can be transferred across Rust threads safely and as said, are implemented to most Rust's internal types.

There are only some small exceptions including the ``Rc`` smart pointer as stated [here](./State_sharing), as both threads could accidentally update counts simultaneously.

## The ``Sync`` trait
The ``Sync`` trait represents that a type's reference can be held across threads safely and therefore be sent safely to another thread.

Just as the ``Send`` trait, it is implemented across many of Rust's built-in types, with just a few couple exceptions.: including again the ``Rc`` trait and this time the ``RefCell`` too.