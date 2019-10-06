>*Note: This repository primarily serves as a submodule for `LittleEngine` (and is bound by the same licence), but is completely standalone and free to be used in any other projects.*

### LittleEngine Delegate

*Copyright 2019 Karn Kaul*

Features:
- Header-only
- Variadic template class providing `std::function<void(T...)>` (any number of parameters)
- Supports multiple callback registrants (thus `void` return type for each callback)
- Token based, memory safe lifetime

Usage:
- Create a `Delegate<>` for a simple `void()` callback, or `Delegate<T...>` for passing arguments
- Call `Register()` on the object and store the received `Token` to receive the callback
- Invoke the object (`foo()`) to fire all callbacks; returns number of active registrants
- Discard the `Token` object to unregister a callback (recommend storing as a member variable for transient lifetime objects)
