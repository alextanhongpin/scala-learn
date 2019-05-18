Unlike array/list, tuple index starts from 1.

```scala
val ingredient = ("sugar", 10)
println(ingredient._1)
println(ingredient._2)

val (sugar, price) = ingredient
println(s"$sugar cost $price")


val planets = List(("Mercury", 57.0), ("Jupyter", 149.4))
planets.foreach {
	case (planet, distance) => println(s"planet is $planet $distance")
  case _ => 
}
for ((planet, distance) <- planets) {
  println(s"$planet $distance")
}
```
