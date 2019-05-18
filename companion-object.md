# Companion Object

Using companion object to encapsulate methods, and also as a factory function to create the class.

```scala
class Location (a: Int = 0, b: Int = 0) {
  // Imports all methods from the object Location.
  // To just import specific method, do Location.method_name, e.g. Location.printLocation
  import Location._
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
  // Factory object. Cannot be private.
  def fromPoint(x: Int, y: Int): Option[Location] = {
    Some(new Location(x, y))
  }
}

val location = new Location()
location.move(10, 20)

Location.fromPoint(20, 10) match {
  case Some(loc) => loc.move(2, 1)
  case None => println("no location available")
}
```
