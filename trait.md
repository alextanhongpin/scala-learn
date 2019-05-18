```scala
trait Equal {
  def isEqual(x: Any): Boolean
  def isNotEqual(x: Any): Boolean = !isEqual(x)
}

// xc, yc stands for x-, y-constructor respectively.
class Point(xc: Int, yc: Int) extends Equal {
  var x: Int = xc
  var y: Int = yc
  def isEqual(obj: Any) = obj.isInstanceOf[Point] && obj.asInstanceOf[Point].x == x && obj.asInstanceOf[Point].y == y
}

val p1 = new Point(1, 2)
val p2 = new Point(1, 2)
println(p1.isEqual(p1))
println(p1.isEqual(p2))
```
