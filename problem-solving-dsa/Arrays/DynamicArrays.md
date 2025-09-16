# Dynamic Arrays 

A Dynamic array automatically grows when we try to make an insertion and there is no more space left for the new item. 
Usually the capacity doubles in size.

# Drawback of Arrays
The drawback of the regular array, is the size of the array cant be adjusted during the code execution. (i.e the size is fixed and defined during the array intilization)

In, other words it will fail to add the (n+1)th element if we allocate an array size equal to n. 

One solution would be to allocate a large array, but this could waste a significant amount of memory.

Here is an idea: We can use the idea of dynamic array, where we can increase the array size dynamically as we need it. 

# How does Dynamic array work ?
Suppose we start with an array size 1 and double its size whenever we run of space. This process will allocate a new array of double size, copy the data of the old array to the lower half of the new array, and delete the space used by the old array. 

***The crirical question:*** how many times does an element need to be recopied after n number of insertions? 

This doubling process continues, if we insert the 2th, 4th, 8th, 16th, 32nd.... elements. In general, after the i number of doubling, the new array size would be 2^i, ad there will be 2^(i-1) elements in the array. So there is no need to resize the array from 2^(i-1) + 1 to 2^i - 1 insertion. 

After, the 2^i the insertion, the array will get full, and we need to double the array size to 2^(i+1) and copy the 2^i elements  in the new array. 

![Dynamic array usage](https://cdn-images-1.medium.com/max/960/1*9s7_mGUIzA_JcOOw-zQh9Q.png)