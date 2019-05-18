```scala
class Location (a: Int = 0, b: Int = 0) {
  import Location.printLocation
  var x: Int = a 
  var y: Int = b
  def move(dx: Int, dy: Int) {
    x = x + dx
    y = y + dy
    printLocation(x, y)
  }
}

object Location {
  private def printLocation(x: Int, y: Int) {
    println(s"location is now ($x, $y)")
  }
}

val location = new Location()
location.move(10, 20)
```
