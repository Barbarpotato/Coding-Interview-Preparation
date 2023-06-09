# Working with time complexity
## Big-O notation
In this reading, you will explore a worked example of a piece of code written in Python, along with how you would evaluate it using Big-O notation. 

Evaluating an application's performance ensures that the code written is good and fit for purpose. The question is how do we evaluate efficiency? When we measure electricity, we use kilowatt-hours, which means how many kilowatts an appliance will use if it runs for an hour. The appliance will not always run for an hour, and it may have different requirements depending on the setting used, it is more of a general rule-of-thumb for evaluating cost. 

When evaluating coding solutions, Big-O notation is used. So, Big-O notation is the kilowatt hour of code evaluation. It can be applied to measuring how much time a piece of code will take or how much space it will use in memory. Not all processors will run at the same speed, so instead of timing an application, you count the number of instructions an application initiates. 

Which measurement reflects the quickest possible execution of some code?
Let's explore which measurement reflects the quickest possible execution of some code.

`O(1)`
You use a constant time algorithm that takes O(1) (O-of-one) time to compute. This determines that it will only take one computation to complete a task. An example of this is to print an item from an array. 
```python
# An array with 5 numbers 
array = [0,1,2,3,4]

# retrieve the number found at index location 3 
print(array[3]) 
```
In this instance, no matter how many values exist in the array, the approach has a Big-O of one. This means that running this code is considered O(1). 

`O(n)`
Next, let's explore an example of O(n). Taking the same array, an if statement is written that looks for the number 5. To establish that 5 is not there, it has to check every item in the array. 
```python
# An array with 5 numbers 
array = [0,1,2,3,4] 

if 5 in array:
    print("five is alive")
```
In the above example, there is no 5, so there is no printout. To establish this, five checks were made on this array. As the input n = 5, this code is said to have a Big – O of O(n). To better understand this, let's extend the array to 10, leaving out the 5. 
```python
# an array with 10 numbers 
array = [0,1,2,3,4,6,7,8,9,10]

if 5 in array:
    print("five is still alive")
```
`O(log n)`
This search is less intensive than O(n) but more work than O(1). O(log n) is a logarithmic search and it will increase as new inputs are added but these inputs only offer marginal increases. An excellent example of this in action is a binary search. Binary search is covered in more detail later in the course. 

Now, imagine playing a guessing game with the following prompts: too high, too low, or correct. You are given a range of 100 to 1. You may decide to approach the problem systematically. First, you guess 50 – too high. So, you guess 25 – which is too high. You may choose then to go 12 or 13. What is happening here is that you are halving the search space with each guess. 

So, while the input to this function was 100 using a binary search approach, you should come upon the answer in under 5 or 6 guesses. This solution would have a time complexity of O(log n). Even if n (the range of numbers entered) is ten times bigger. It will not take ten times as many guesses. 

Here is a breakdown of those steps on the array. 
```python
array = [0,1,2,3,4,6,7,8,9,10]

print("##Step One")
print("Array")
print(array)
midpoint = int(len(array)/2)
print("the midpoint at step one is: " , array[midpoint])

print()

print("##Step Two")
array = array[:midpoint] # 6 is the midpoint of the array 
print("Array")
print(array)
# running this shows the numbers left to check 
# is 5 < 3 
# no 
# so discard the left hand side 

# so the array is halved again 
midpoint=int(len(array)/2)
print("the midpoint is: ",  array[midpoint])

print()
print("##Step Three") 
array = array[midpoint:] # so the array is halved at the midpoint
print(array)# check for the midpoint 
midpoint=int(len(array)/2)
print("the midpoint is: " , array[midpoint])
# is 4 < 5 
# yes look to the right

print()
print("##Step Four") 
print(array[midpoint:]) 
# check for the midpoint 
array = array[midpoint:] # so the array is halved at the midpoint
midpoint=int(len(array)/2)



print()
print("##Step Five") 
array = array[midpoint:] 
print(array)
print("only one value to check and it is not 5")
```
You will notice that to determine if 5 is present, it took 5 steps. That is a big-O score of O(5). You can see that this is bigger than O(1) but smaller than O(n). Now, what happens when the array is extended to 100? When looking for a number in an array of 10, it took 5 guesses. Looking at an array of 100 will not take 50 guesses; it will take no more than 10. Equally, if the list is extended to 1000, the guesses will only go up to 15-20. 

From this, we can see that it is not O(1) because the answer is not immediate. It is not big-O(n) because the number of guesses does not go up with the size n of the array. So here, one says that the complexity is O(log(n)). 

To gain greater insight into how the log values are only a gradual rise, look at a log table up to 100,000,000. This lens shows that O(log n) incurs only a minimal processing cost. Running a binary search on an array with any n values will, in a worst-case scenario, always make the number of computations found in the log values column. 

`O(n^2)` is heavy on computation. This is quadratic complexity, meaning that the work is doubled for every element in the array. An excellent way to visualize this is to consider that you have a variety of arrays. In keeping with the earlier example, let's explore the following code:
```python
new_array=[] # an array to hold all of the results 
# array with five numbers 
array = [0,1,2,3,4]
for i in range(len(array)): # the array has five values, so this is n=5 
    for j in range(len(array)): # still the same array so n = 5 
        new_array.append(i*j) # every computation made is stored here 

print(len(new_array)) #how big is this new array ? 
```
The first loop wi   ll equal the number of elements input, n. The second loop will also look at the number of input elements, n. So, the overall complexity of running this approach can be said to be n*n which is n^2 (n-squared). To find out how many computations were made, you have to print out the number of times n was used in the loop as below.

If you know that the array has 25 elements, then you understand the principles of calculating Big-O notation. To further test your knowledge, how many computations would be required if n = 6? Meaning the array had 6 values? The answer is 6 x 6 so 36. 

# Working with Space Complexity
Some Algorithms like `hash tables` provide very fast lookups in `O(10) time`. However, to work efficiently, they must have a lookup every element stored. This results in a space complexity of O(n). The big O-notation for space complexity is the same as for the time O(1), O(log log n), O(log n) and so on.
In all these notations `n` refers to the size of the input. This is often measured in bytes.

 Different languages have different memory costs associated with them. In java for instance, an integer requires 4 bytes of memory. A blank array will consume 12 bytes for the header object and an additional 4 bytes for padding. Thus, if n refers to an array of integers size 4, then the total memory requirement is 32 bytes of memory.
`(4 * 4) + 12 + 4 = 32`

When discussing space complexity, you have to consider what the increase in input size has on the overall usage. Space Compexity is the total of auxiliary space + input space The space complexity of a problem can be broken into two sections namely auxiliary and input space:
- Auxiliary space is the space required to hold all data required for the solution. It refers to the temporary space needed to compute a given solution.
- Input space refers to the space required to add data to the function, algorithm, application or system that you are evaluating.

Example:
```js
const a = 1;
const b = 10;
const c = 100;
const sum = (a, b, c) => a + b + c;
const d = sum(a, b, c);
```
In the above function sum, we can resolve the space complexity required by the memory requirement. Given that all arguments in the above example are integers and the return value is an integer of set size, we know this will be constant.

Given the Number type in JavaScript is 64-bit (8 bytes), we can resolve that the memory requirement for a, b and c is (24). Therefore, the function sum has `O(1)` constant space complexity given that we know the constant requirement of 24 bytes of data space for this function.

Looking at an example in C that requires a dynamic amount of memory in an array:
```c
int sum(int a[], int n) {
    int x = 0;      // 4 bytes for x
    for(int i = 0; i < n; i++)  // 4 bytes for i
    {
        x  = x + a[i];
    }
    return(x);
}
```
Firstly, we know that int types in C require 4 bytes of space. Here we note that 4*n bytes of space is required for the array a[] of integers. The remaining variables x, n, i and the return value each require a constant 4 bytes each of memory give that they are integers.

This gives us a total memory requirement of (4n + 12). This itself is `O(n)` linear space complexity since the memory requires linearly increases with input value n.

What is important to note with this example is that the auxiliary space required for the above sum function is actually  `O(1)` constant given that the auxiliary variables are only x and i which totals a (8) memory requirement (constant).
