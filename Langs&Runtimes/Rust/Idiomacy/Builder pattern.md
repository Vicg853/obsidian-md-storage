Sometimes, when building data type and using a ``::new()`` method pattern, things may get tangled, with many ``::new_something()`` sub methods, to define optional fields and etc.

When we stumble with this problem, we may use the builder pattern, that works with a method for each field and a final ``.build()`` method, that will return our desired struct. 

Consider a struct ``MyServer``, which requires the definition of both a ``host``and ``port`` variables, and both a ``tls`` and ``hot_reload`` fields, which are optional (wrapped by the ``Option`` enum). 
We will define a ``MyServerBuilder`` struct, containing the same fields and implement a method for each optional one, which receive the underlying field as argument, along a mutable reference to self. 
Finally, we define a ``build`` method, to be called at the end, which will return a ``MyServer`` instance. Finally, we may implement a ``new`` method to ``MyServer``, which returns a ``MyServerBuilder`` instance, with optional fields initially defined as ``None``.

## Example code
```rust
struct MyServer {
	host: String,
	port: i32,
	tls: Option<Cert>,
	hot_reload: bool
}

impl MyServer {
	fn new(host: String, port: i32) -> MyServerBuilder {
		MyServerBuilder {
			host,
			port,
			tls: None,
			hot_reload: None
		}
	}
}

struct MyServerBuilder {
	host: String,
	port: i32,
	tls: Option<Cert>,
	hot_reload: Option<bool>
}

impl MyServerBuilder {
	fn tls(&mut self, tls: Cert) -> &mut self {
		self.tls = tls
	}
	fn hot_reload(&mut self, hr: bool) -> &mut self {
		self.hot_reload = hr
	}
	fn build(&mut self) -> &self {
		MyServer {
			host: self.host.clone(),
			port: self.port.clone(),
			tls: self.tls.unwrap_or_default(),
			hot_reload: self.tls.unwrap_or_default()
		}
	}
}
```

Now when calling, instead of different functions for each definition case we may wan't to use, we simply do:

(consider the code defined above)
```rust
let server = MyServer::new()
	.tls(some_tls_config)
	.hot_reload(true)
	.build();
```