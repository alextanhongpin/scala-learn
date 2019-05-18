## List comprehension

```scala
case class User(name: String, age: Int)

val userBase = List(User("Travis", 28),
	User("Kelly", 33),
	User("Jennifer", 44),
	User("Dennis", 23))

val twentySomethings = for (user <- userBase if (user.age >= 20 && user.age < 30))
	yield user.name

println(twentySomethings.mkString(", "))
```


## Generic List

```scala
class Stack[T] {
  private var elements: List[T] = Nil
  def push(x: T) { elements = x :: elements }
  def peek: T = elements.head
  def pop(): T = {
    val currentTop = elements.head
    elements = elements.tail
    currentTop
  }
}

val stack = new Stack[Int]
stack.push(1)
println(stack.peek)
println(stack.pop())
```
