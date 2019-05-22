
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

>  - #### **Fibonacci Sequence** - *commonly denoted Fn form a sequence*
##### Formula: fibonacci in Kotlin
   
    private fun fibonacci(n: Int): Int {  
	    return if (n <= 1) n else fibonacci(n - 1) + fibonacci(n - 2)  
    }
>  - #### **Factorial** - *In mathematics, the **factorial** of a positive integer n, denoted by n!, is the product of all positive integers less than or equal to n.*
##### Formula: factorial in Kotlin
   
    private fun factorial(n: Int): Int {  
	    return if(n==1) n else factorial(n - 1) * n  
	}

>  - #### **Permutation** - *to get each of several possible ways in which a set or number of things can be ordered or arranged.*
##### Formula: permutation in Kotlin

    private fun <T> permutation(input: List<T>): List<List<T>> {  
	    
	    if (input.size == 1) 
		    return listOf(input)  
	    
	    val perms = mutableListOf<List<T>>()  
	    val toInsert = input[0]  
	    for (perm in permutation(input.drop(1))) {  
		    for (i in 0..perm.size) {  
			    val holdNew = perm.toMutableList()  
			    holdNew.add(i, toInsert)  
			    perms.add(holdNew)  
     } 
     }  return perms  
    }  
      
    fun mains(args: Array<String>) {  
      val input = listOf('a', 'b', 'c', 'd')  
      val permutation = permutation(input)  
      println("There are ${permutation.size} permutations of $input, namely:\n")  
      for (perm in permutation) println(perm)  
    }

## Bitmask Operations
> Bit masking allows you to use operations that work on bit-level. Which often leads to faster runtime and limits memory usage

##### Formula: swap values with only two variables in Kotlin
   

    var x=1  
    var y=10  
      
    x = x xor y  
    y = y xor x  
    x = x xor y

##### Formula: Multiple by 2n in Kotlin
   
    var j = 20
    var n = 2
    
    print(j shl n) // 80

##### Formula: Divided by 2n in Kotlin
   
    var j = 20
    var n = 2
    
    print(j shr n) // 5

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk0OTAzMzIwMiwxMzQxNzc0OTI5LC0xNz
gxMjQ5MTgsNjc1MDQxMTQsMTc0NTAwOTA2Niw3NTQ5MjQ1NjQs
MzQ5NDg4NTU1XX0=
-->