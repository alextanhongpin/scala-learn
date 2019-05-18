```scala
def add(x: Int)(y: Int): Int = x + y

// Must have the underscore _
val addFive = add(5)_
println(addFive(10))
```
