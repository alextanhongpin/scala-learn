```scala
def apply(user: String, domain: String) = {
  s"$user@$domain"
}
def unapply(str: String): Option[(String, String)] = {
  val parts = str split "@"
  if (parts.length == 2) {
    Some(parts(0), parts(1))
  } else {
    None
  }
}

println(apply("john", "gmail.com"))
println(unapply("john.doe@gmail.com"))
println(unapply("johnny"))

```
