We could call trait bounds: "by trait type limitations". They help you infer and limit a [generic's](./Generics), variable, argument and etc. types in a very particular way: by using traits. 

If we take a function's example: you can narrow its argument ``a`` so it only accepts types that implement the ``Copy`` trait. 
Now when calling that function and passing an argument, of a type that does not implement the trait ``Copy`` it will not be accepted as a valid argument.

They can be defined after columns just like a normal type and are accepted everywhere just like any other type annotation.

```rust
struct A<T: Display + Clone> {
	//...
}

fn my_func<T: Display>(arg: &T) {
	//...
}
```

## Trait bounds' syntax sugar for funcs
#### Args
We may use the ``impl`` keyword sometimes, to make trait bound definitions shorter, instead of using a generic or the [``where``](./Generics##``where``) keyword.

You use it like a common type definition, after column

```rust
fn my_func1(arg: &impl Copy) -> i64 {
	//...
}
```
Not this function will only accept arguments that implement the ``Copy`` argument, in the same way as if we had defined this with generics or ``where``.

#### return
The same can be applied to return types
```rust
fn my_func2(&self) -> impl MyTrait {
	//...
}
```

Now, the return type may be anything that implements the ``MyTrait`` trait.

> _Caution note:_ you can't return two or more types, even if all of them implement the return trait type. 

> Take this as an ilegal example:
```rust
fn my_func3(is_true: bool) -> impl MyTrait {
	if is_true {
		MyStructThatImplsMyTrait {
			//...
		}
	} else {
		MySecondStructThatImplsMyTrait {
			//...
		}
	}
}
```