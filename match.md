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
}```
