```scala
// This contains Future and ExecutionContext
import scala.concurrent._
import scala.concurrent.duration.Duration
import scala.concurrent.forkjoin._
import scala.util.{Success, Failure}

import ExecutionContext.Implicits.global
// implicit val ec = ExecutionContext.global

val future = Future {
  Thread.sleep(1000)
  1
}

// This will not wait for the thread to complete.
// println(future)
// future onComplete {
//   case Success(res) => println(s"success $res")
//   case Failure(e) => println(s"an error has occured $e")
// }

Await.ready(future, Duration.Inf) onComplete {
  case Success(res) => println(s"success $res")
  case Failure(e) => println(s"an error has occured $e")
}
```
