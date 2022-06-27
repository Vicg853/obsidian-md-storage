## Functions imports
Functions should be used with their module definition for easier identification:
```rust
pub my_mod;
pub my_mod2;

my_mod::func();
my_mod2::func();
//...
```

## Enums and Struct imports
Struct and enums should be brought directly into scope and used with no module path before, UNLESS there are naming conflicts. In that case either ``as``  or the module path should be used.

#### no conflict
```rust
pub my_mod::{CarStruct};
pub my_mod2::{BusStruct};

let my_car = CarStruct {
	//...
};

let my_bus = BusStruct {
	//...
};
```

#### With conflics
```rust
pub cars;
pub ariplanes::{Chassis as PlaneChassis};

let my_car = PlaneChassis {
	//...
};

let my_bus = cars::Chassis {
	//...
};
```
