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
for (x <- arr) {
  println(x)
}
```
