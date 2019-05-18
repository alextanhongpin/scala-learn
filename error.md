```scala
def work() = {
  	// throw new IllegalArgumentException
  throw new Exception("invalid work")
}

try {
	work()  
} catch {
  case ex: IllegalArgumentException => {
    println("illegal argument")
  }
  case ex: Exception => {
    println(ex)
  }
  case _: Throwable => println("error occured")
}

// Option, Some, None
def toInt(s: String): Option[Int] = {
  try {
    Some(Integer.parseInt(s.trim))
  } catch {
    case e: Exception => None
  }
}

toInt("a") match {
  case Some(n) => println(s"success: $n")
  case None => println("failed")
}

// Try/Success/Failure
import scala.util.{Try,Success,Failure}

def toInt2(str: String): Try[Int] = Try {
  Integer.parseInt(str.trim)
}

toInt2("a") match {
  case Success(i) => println(i)
  case Failure(e) => println(e)
}
```
