## Higher order function
```scala
val salaries = Seq(100, 200, 300)
val doubleSalary = (x: Int) => x * 2
val doubleSalaries = salaries map doubleSalary
println(doubleSalaries)

val newSalaries = salaries map (_ * 2)
println(newSalaries)
```

## Refactoring with higher order function
```scala
object SalaryRaiser {
  private def promotion (salaries: List[Double], promotionFunction: Double => Double) = salaries.map(promotionFunction)
  
  def smallPromotion(salaries: List[Double]): List[Double] =
  	// salaries.map(_ * 1.1)
  	promotion(salaries, (salary => salary * 1.1))
	
  def greatPromotion(salaries: List[Double]): List[Double] =
  	// salaries.map(salary => salary * math.log(salary))
  	promotion(salaries, (salary => salary * math.log(salary)))

  def hugePromotion(salaries: List[Double]): List[Double] =
  	// salaries.map(salary => salary * salary)
  	promotion(salaries, (salary => salary * salary))
}

println(SalaryRaiser.hugePromotion(List(100.0, 200.0)))
```

## Function that returns function
```scala
def urlBuilder(ssl: Boolean, domainName: String): (String, String) => String = {
  val schema = if (ssl) "https://" else "http://"
  (path: String, qs: String) => s"$schema/$domainName/$path?$qs"
}
val builder = urlBuilder(ssl=true, domainName="john.doe")
println(builder("home", "limit=10"))
```
