## Intro
Generics in a nutshell can be compared to typing variables: types that aren't exactly defined.
You may use them in functions, struct, implementations and Enums, inside "``<``"  "``>``" and just like variables, can have any name.
They are useful to define variable types in cases where a same piece of code used across multiple argument, self, etc. types

A nice thing to know, is that, generic types are replaced by its type in each of its use case, so... no performance bottlenecks trying to discover types.
An even better thing: the Rust compiler actually takes types very seriously, so you are able to even query a certain struct element by its generic types: [[#Querying types in bevy example]]


## Main e.g.s:
- For functions: 
```rust
	// Now the t arg must be equal the generic passed,
	// or T will be defined as t type in case it is not implicitly defined by you
	fn my_func<T>(t: T) -> T {
		t //This will be equal the T type
	}
```
- For Enums
```rust
	// The value passed to Some must have the same type as U
	enum Option<U> {
		Some(T),
		None
	}
```
- Finally for structs and implementations
```rust
	// Here x and y must both:
	// - have the same type as X
	// - share the same type, as both have X type
	struct Cords<X> {
		x: X
		y: X
	}

	// Note that generic types are not shared across structs and impl (and other 
	// impls)
	impl<T> Cords<T> {
		fn getCords(&self) -> &T {
			self
		}
	}
```
- *Also you can define impls for implicit generic struct types* (consider the above example)
```rust
	//Here this implmentations will only be avaible to struct data that have an f32 
	//type
	impl Cords<f32> {
		fn getX(&self) -> &f32 {
			self.x
		}
	}
```


## Multiple generics a time:
```rust
	fn my_func2<T, U>(t: T, u: U) {
		vec![t, u]
	}
```

## Narrowing gen types
Sometimes, you may want to narrow your options. As in a case you are comparing two variables sizes, where not all types can be submitted to it. Then you can define a generic's type

```rust
	//here is how you do it, just as in variables you use ":"
	fn get_largest<T: PartialOrd + Copy>(x: T, y: T) -> T {
		if x > y {
			return x
		}
		return y
	}
```


## Querying types in bevy example
You can use generics to query specific struct data.

Lest consider the following case from the Bevy engine: in bevy, there are "entities", each containing transform and other structs. To make things easier, lets narrow things down, our bevy app has an only entity, a 2D sprite. Let's query him

```rust
	struct 
		mut query: Query<&mut Transform, With<Sprite>>,
	fn move_scene_entities(
		time: Res<Time>,
		mut scene_entities: Query<&mut Transform, With<EntityInMyScene>>,
	) {
		//....
	}
```

See: ``Query`` is a Bevy internal struct, that caries almost all internal bevy resources and at the same time it accepts generics. 
```rust
	//Simplified view
	struct Query {
		entities: Entity
		//Entity looks smth like this
		// {
		//   transform: Transform
		//   sprite: Sprite
		// }
	}
```

And ``Query`` uses rust features to its advantages: as Rust takes types seriously, when using the ``Query`` struct, with a ``Transform`` generic, Rust will return inner ``Query`` data that has a ``Transform`` struct type and the second argument does the same thing, but it narrows even more the search, so now rust will return every ``Transform`` struct type data that also is a ``Sprite`` struct type.