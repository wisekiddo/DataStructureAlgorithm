
# Data Structure and Algorithm Reviewer
Data Structure and Algorithm Reviewer in Kotlin examples

## Algorithms
> a process or set of rules to be followed in calculations or other problem-solving operations, especially by a computer.
> 

 - ### Sorting Algorithms
#### Merge Sort
Mergesort is another divide and conquer algorithm. It continuously divides an array into two halves, recurses on both the left subarray and right subarray stops until it left 1 element, and finally merges the two sorted halves.

This is my favourite sorting algorithm other than it is predictable and used for variety of situations, it has the stability that you can rely on.



##### Stability: High
##### Time Complexity:
|  Best Case|  Worst Case|Average Case|
|--|--|--|
|  O(n log(n)) |  O(n log(n)) |	O(n log(n))|

##### Formula: Mergesort in Kotlin

    fun mergeSortDivide(list: List<Int>): List<Int> {
        if (list.size <= 1) {
            return list
        }

        val median = list.size / 2
        val leftList = list.subList(0,median)
        val rightList = list.subList(median,list.size)

        return mergeConquer(mergeSortDivide(leftList), mergeSortDivide(rightList))
    }


    private fun mergeConquer(leftList: List<Int>, rightList: List<Int>): List<Int>  {
        var indexLeft = 0
        var indexRight = 0
        val newList : MutableList<Int> = mutableListOf()

        while (indexLeft < leftList.count() && indexRight < rightList.count()) {
            if (leftList[indexLeft] <= rightList[indexRight]) {
                newList.add(leftList[indexLeft])
                indexLeft++
            } else {
                newList.add(rightList[indexRight])
                indexRight++
            }
        }

        while (indexLeft < leftList.size) {
            newList.add(leftList[indexLeft])
            indexLeft++
        }

        while (indexRight < rightList.size) {
            newList.add(rightList[indexRight])
            indexRight++
        }

        return newList
    }



## Data Structures
> is a way to store and organise data so that it can be used efficiently.



## Formula
> **mathematical** symbols or rules that express a relationship or that are used to solve a problem, or a way to make something

>  #### **Fibonacci Sequence** - *commonly denoted Fn form a sequence*
##### Formula: fibonacci in Kotlin
   
    private fun fibonacci(n: Int): Int {  
	    return if (n <= 1) n else fibonacci(n - 1) + fibonacci(n - 2)  
    }
>  #### **Factorial** - *In mathematics, the **factorial** of a positive integer n, denoted by n!, is the product of all positive integers less than or equal to n.*
##### Formula: factorial in Kotlin
   
    private fun factorial(n: Int): Int {  
	    return if(n==1) n else factorial(n - 1) * n  
	}

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0MjM4MzE2NzAsNzU0OTI0NTY0LDM0OT
Q4ODU1NV19
-->