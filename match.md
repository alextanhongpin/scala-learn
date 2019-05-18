# Matching in loop

```scala
sealed abstract class Notification

case class Browser(val msg: String) extends Notification
case class Mobile(val msg: String) extends Notification

var notifications = List(Browser("ho"), Mobile("ha"))

// With foreach
notifications.foreach(notification =>
  notification match {
    case Browser(msg) => println(s"${msg} received for browser");
    case Mobile(msg) => println(s"${msg} received for mobile");
  }
)


// with for loop
for (notification <- notifications) {
  notification match {
    case Browser(msg) => println(s"${msg} received for browser");
    case Mobile(msg) => println(s"${msg} received for mobile");
  }
}
```

## Matchin environment

```scala
def matchEnvironment(env: String) = env match {
  case "development" => println("is dev")
  case "production" => println("is prod")
  case _ => println("unknown")
}

matchEnvironment("production")
```

## Matching case class
```scala
case class Person(name: String, age: Int)

val john = new Person("john", 20)
john match {
  case Person(name, age) => println(s"$name is $age years old")
  case _ => println("unknown person")
}
```
