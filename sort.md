## Insertion Sort
```scala
def insertionSort(nums: Array[Int]) {
  for (i <- 0 until nums.length) {
    var j = i
    while (j > 0 && nums(j-1) > nums(j)) {
      val tmp = nums(j-1)
      nums(j-1) = nums(j)
      nums(j) = tmp
      j = j - 1
    }
  }
}

val arr = Array(-1,4,3,2,1)
insertionSort(arr)
println(arr.mkString(",")
```


## Selection Sort

Selects the smallest value and swap it with the most left position.
```scala
def selectionSort[T:Numeric](nums: Array[T])(implicit ord: Ordering[T]) = {
	for (i <- nums.indices) {
  	var pos = i
    for (j <- i + 1 until nums.length) {
      if (ord.lt(nums(j), nums(i))) {
        pos = j
      }
    }
    val tmp = nums(pos)
    nums(pos) = nums(i)
    nums(i) = tmp
  }
}

val in: Array[Long] = Array(5,4,3,2,1)
selectionSort[Long](in)
println(in.mkString(","))
```
