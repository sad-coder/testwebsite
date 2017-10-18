General
-------

**Is Scala a pure OOP language? Is Java a Pure OOP Language?**

Pure object-oriented programming language means everything is an object.
Java is not a pure object-oriented programming language due to non object-oriented concepts:
Java has primitive data types (`int`, `long`, `boolean`, `char` etc.) which are not objects.
Java supports static members. They are not related to objects.
Scala is a pure Object-Oriented Programming panguage because in Scala, everything is an Object and everything is a value. Functions are values and values are Objects. Scala does not have primitive data types and does not have static members.

**What is the difference between** `var`**,** `val` **and** `def`**?**

A var is a variable. It’s a mutable reference to a value. Since it’s mutable, its value may change through the program lifetime. Keep in mind that the variable type cannot change in Scala. You may say that a var behaves similarly to Java variables.
A val is a value. It’s an immutable reference, meaning that its value never changes. Once assigned it will always keep the same value. It’s similar to constants in another languages.
A def creates a method (and a method is different from a function - thanks to AP for his comment). It is evaluated on call.
def is short for "define". It’s a keyword that you need to define a function.

**What is the difference between** `val` **and** `lazy val`**?**

`val` is executed when it's defined whereas `lazy val` is executed when it's accessed for the first time.

**What is the difference between evaluation strategies** _call-by-value_ **and** _call-by-name_ **parameter?**

_Call-by-value_ is computed before calling the function:
```scala
scala> def Id(x: Int) = x
Id: (x: Int)Int
```

_Call-by-name_ parameter is evaluated when accessed:
```scala
scala> def Id(x: => Int) = x
Id: (x: => Int)Int
```

**Short-circuit evaluation**



**What is the purpose of** `apply` **method?**

It allows to write `someObject(params)` instead of `someObject.apply(params)`. Widely used in case classes which contain a companion object with `apply` method.

**What is the purpose of** `unapply` **method?**

`unapply` takes an object and tries to give back the arguments. This is most often used in pattern matching and partial functions. The return type of an unapply should be chosen as follows:

- If it is just a test, return a `Boolean`
- If it returns a single sub-value of type `T`, return an `Option[T]`
- If you want to return several sub-values `T1,...,Tn`, group them in an optional tuple `Option[(T1,...,Tn)]`

Object oriented programming
---------------------------

**What is the difference between** `object` **and** `class`**?**

An object is a singleton instance of a class. It does not need to be instantiated. If an object has the same name that a class, the object is called a companion object.

**What is companion object?**

If an object has the same name that a class, the object is called a companion object. Companion object can access private members of class and vice versa.

**What is** `case class`**?**

Case class has already implemented `equals`, `hashCode`, `apply` and `unapply` methods. It also defines getter methods for the constructor arguments are passed without `val` keyword.

#That adds the following features to it:
#
#- `apply` no `new` preceding keyword is needed for instantiation of the case class
#- `unapply` allows the case class to be pattern matched
#- `equals` adds object equality
#- `hashCode` 

**What is** `trait`**?**

Traits are similar to Java's interfaces and cannot be instantiated and therefore have no parameters.
