```scala
class Point(a: Int = 0, b: Int = 0) {
  var x: Int = a
  var y: Int = b
  def move(dx: Int, dy: Int) {
    x = x + dx
    y = y + dy
    println(s"point is now at ($x, $y)")
  }
}

val point = new Point()
point.move(10, 20)

class Location(a: Int = 0, b: Int = 0, c: Int = 0) extends Point(a, b) {
  var z: Int = c
  def move(dx: Int, dy: Int, dz: Int) {
    x = x + dx
    y = y + dy
    z = z + dz
    println(s"point is now at ($x, $y, $z)")
  }
}

val location = new Location()
location.move(10, 20)
location.move(-1, -5, 10)
```
