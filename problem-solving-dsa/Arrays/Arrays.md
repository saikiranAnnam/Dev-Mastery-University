# Arrays

An array is a collection of elements, all of the same type, stored in the contiguous memory locations. 

***Indexing:*** Arrays use zero-based indexing, meaning the first element is at index `0`.

***Fixed Size:*** The size of an array is determined when it is created and cannot be changed. 

Index : 0   1   2   3   4
Array :[10, 20, 30, 40, 50]

## Why use Arrays?
* Fast Access : Accessing the elements by index is quick O(1). 
* Organized Storage : Ideal for storing a fixed number of items of the same type. 
* Foundation : Used in many advanced data structures like stacks, queues and heaps. 

***Key Features:***
Fixed Size (define the size of the array beforehand)
Indexing(accessing the element using their index)
Homogeneous Elements (all elements of same type)

***Python:***
```python
# array creation
numbers = [10, 20, 30, 40, 50]

# accessing the elements in the array
print(number[0])
print(number[1])
print(number[2])

# modify the element in the array
numbers[1] = 80 
print(number[1])
```

***Java:***
```java
int[] numbers = {1, 2, 3, 4, 5};
String[] names = {"John", "Smith", "Jack", "Queen"};

# how to declare an array with default values 
# datatype[] arrayName = new datatype[length]
int[] numbers = new int[5];
# here, we declare an array of integers named numbers with the 
default size of size of 5. as we didnt specify the values in the 
array, each element in the array is by default value `0`. 
```



