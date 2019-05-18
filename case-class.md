```scala
case class Point(x: Int = 0, y: Int = 0)
val p1 = Point(10, 20)
val p2 = Point()
val p3 = Point(10, 20)
println(p1)
println(p2)

println(p1 == p3)
```
