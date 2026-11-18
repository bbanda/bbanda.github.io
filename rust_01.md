## Rust – Questions & Answers ##

**1. Why can we not simply copy a String?**

This is because a String is essentially a pointer to a Vec<u8> with some metadata. If we copy this, then we would have multiple unconstrained pointers to the same string data, which could introduce errors with concurrency, mutability, and lifetimes.

**2. Rust has strong typing. In which two ways can we enable a container such as a vector or hashmap to contain multiple different types?** 

There are two ways:

Using an Enum: We can use an enum, which means that the type being accepted into the container can be one of the types defined in the enum. When reading the data, we can then use a match statement to manage all possible data types that could be read from the container.
Using Traits: We can create a trait that multiple different structs implement. However, when reading data from the container in this case, the available interactions are limited to the functions defined by the trait.

**3. How are Python decorators and Rust macros the same?**

They both wrap around code and alter the implementation or attributes of the code they are wrapping without directly returning anything.

**4. What is the Python equivalent to a main function in Rust?** 

The Python equivalent is:

python
if __name__ == "__main__":

**5. Why can we get a higher integer value with the same number of bytes with an unsigned integer than a signed integer?**

A signed integer must accommodate both positive and negative values, whereas an unsigned integer only accommodates non-negative values. Therefore, an unsigned integer can use all its bits to represent non-negative values, giving it a higher maximum value with the same number of bytes.

**6. Why do we have to be strict with lifetimes and scopes when coding in Rust?** 

Rust does not use garbage collection. Instead, variables are dropped when they go out of scope. If we do not consider lifetimes, we could reference a variable that has already been dropped.

**7. Can we reference a variable when it has been moved?** 

No. The ownership of the variable has essentially been moved, and the original variable can no longer be used.

**8. What can you do to an original variable if it is currently being borrowed in an immutable state?** 

We can still read and create additional immutable references to the original variable. However, we cannot perform a mutable borrow while an immutable borrow is active.

**9. What can you do to an original variable if it is currently being borrowed in a mutable state?** 

We cannot access the original variable while the mutable borrow is active. This prevents other references from observing or modifying the value while it may be changing.
