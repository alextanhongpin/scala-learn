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


## Matching with guard
```scala
abstract class Notification

case class Email(sender: String, title: String, body: String) extends Notification
case class SMS(caller: String, message: String) extends Notification
case class VoiceRecording(contactName: String, link: String) extends Notification

def showNotification(notification: Notification) = {
  notification match {
    case Email(sender, title, _) =>
    	println(s"$sender sent an email with the title $title")
    case SMS(caller, message) =>
    	println(s"received $message from $caller")
    case VoiceRecording(contactName, link) =>
    	println(s"got voice recording $contactName with $link")
  	case _ =>
    	println("unknown notification")
  }
}
val someSMS = SMS("+123456789", "hi")
showNotification(someSMS)
val someVoice = VoiceRecording("john", "link")
showNotification(someVoice)


def showImportantNotification(notification: Notification, importantPeopleInfo: Seq[String]) = {
  notification match {
    case SMS(num, msg) if importantPeopleInfo.contains(num) =>
    	println(s"important sms from $num with message $msg")
    case _ => showNotification(notification)
  }
}

val importantPeopleInfo = Seq("+123456789")
showImportantNotification(someSMS, importantPeopleInfo)
```
