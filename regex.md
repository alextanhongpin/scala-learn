```scala
import scala.util.matching.Regex

val pattern = "scala".r
val str = "scala is scalable and cool"

pattern findFirstIn str match {
  case Some(ptrn) => println(s"found $ptrn")
  case None => println("no matches found")
}
```
