```scala
object Run {
  implicit class IntTimes(x: Int) {
    def times(y: Int): Int = {
      x * y
    } 
  }
  implicit class StringGreet(str: String) {
    def greet(name: String) {
      println(s"$str: hello $name")
    }
  }
}

import Run._
println(5 times 3)
"john" greet "jane"
```
