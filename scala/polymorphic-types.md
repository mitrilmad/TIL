#polymorphic types

##TYPES AND EVALUATION

Type parameters do not affect evaluation in Scala.

We can assume that **all type parameters and type arguments are removed before evaluating the program.**

This is also called **_type erasure._**

Languages that use type erasure include Java, Scala, Haskell, ML, OCaml.

Some other languages keep the type parameters around at run time, these include C++, C#, F#.

##POLYMORPHISM

In programming it means that
-the function can be applied to arguments of many types, or
-the type can have instances of many types.

We have seen two principal forms of polymorphism:
-subtyping: instances of a subclass can be passed to a base class
-generics: instances of a function or class are created by type parameterization.
