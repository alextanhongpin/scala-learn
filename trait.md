## Equal Trait

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


## Iterator Trait
```scala
trait Iterator[A] {
  def hasNext: Boolean
  def next(): A
}

class IntIterator(to: Int) extends Iterator[Int] {
  private var current = 0
  override def hasNext: Boolean = current < to
  override def next(): Int = {
    if (hasNext) {
      val t = current
      current += 1
      t
    } else 0
  }
}

val iterator = new IntIterator(10)
iterator.next()
iterator.next()
println(iterator)
```

## Another Iterator Example
```scala
abstract class AbsIterator {
  type T
  def hasNext: Boolean
  def next(): T
}
class StringIterator(s: String) extends AbsIterator {
  type T = Char
  private var i = 0
  def hasNext = i < s.length
  def next() = {
    val ch = s charAt i
    i += 1
    ch
  }
}
val name = new StringIterator("john doe")
println(name.next)

trait RichIterator extends AbsIterator {
  def foreach(f: T => Unit): Unit = while (hasNext) f(next())
}

class RichStringIter (val name: String) extends StringIterator(name) with RichIterator
val richStringIterator = new RichStringIter("john doe")
richStringIterator foreach println
```
