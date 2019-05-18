```scala
case class Point(x: Int = 0, y: Int = 0)
val p1 = Point(10, 20)
val p2 = Point()
val p3 = Point(10, 20)
println(p1)
println(p2)

println(p1 == p3)
```

## Copy

```scala
case class Message(msg: String, from: String)

val msg1 = Message("hi", "john")
val msg2 = msg1.copy(msg="hello")
println(msg1)
println(msg2)
```
