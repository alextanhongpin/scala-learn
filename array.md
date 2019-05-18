```scala
val arr = Array(0, 1, 2, 3, 4, 5)
println(s"size is ${arr.size}")
println(s"length is ${arr.length}")
for (x <- arr) {
  println(x)
}

// Compute total.
var total = arr(0)
for (x <- arr) {
  total += x
}
println(s"total is $total")

var max = arr(0)
for (x <- arr) {
	if (x > max) max = x
}
println(s"max is $max")

var b = Array(4,5,6)

import Array.concat
var c = concat(arr, b)
for (x <- c) {
  println(x)
}

import Array.range
var listA = range(0, 10, 1)
for (x <- listA) {
  println(x)
}

// Array methods
// apply
// concat
// copy
// empty
// iterate
// fillra
// ofDim
// range
// tabulate
```
