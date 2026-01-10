Introduction to Arrays

Arrays are data structure which contains similar elements. It contains only one type of data say if it has integers then all it will contain is diff values with int data type  
Array has index which tells the position of the values inside it and it starts from 0 and ends at n-1 where n is the length of the array  
Array\_example \= \[1,2,3,4,5,6\] → length is 6 and the 1st element is at index 0 and last is at index 5  
We do not know where the first element will be stored in the whole memory but say it get stored at position x then all the other elements of the array will be stored continuously after this element like x+1, x+2 and so on

So in interviews follow this rule → Brute Force Solution → Better Solution → Optimised Solution  
We will always have a Brute force solution we may or may not have better and optimised solution

Find the largest number  
Pseudo code

Given → a \= \[1,2,3,4,5,5,8\]  
largest \= a\[0\] or even largest \= 0  
for i=0, i\<n, i++  
If a\[i\] \> largest  
largest \= a\[i\]  
print(largest)

Find second largest element  
We have few approaches and below is the approach

Brute force is again sorting the array and then we know that largest element is a\[n-1\] and so second largest will be a\[n-2\]  
But again the one common case is what if we have an array like below  
a \= \[1,2,3,4,7,7\]  
If we sort a\[n-1\] \= 7 and a\[n-2\] \= 7 as well which is incorrect  
Here what we can do is check is a\[n-1\] \== a\[n-2\] then we go for a\[n-3\] and check again but not the optimal solution  
for i in range n-2 to 0  
if a\[i\] \!= largest  
second\_largest \= a\[i\]  
Break  
Better solution  
We get the largest from the array by following the above logic  
We then create another loop to run through the same array and compare with largest  
Lets say slargest \= INT\_MIN or say slargest \= \-1  
We traverse the array again and then check if the element is largest than slargest and then also checks with the flargest element if it is largest than slargest and smaller than flargest then we assign the value to slargest and traverse the array and then get the slargest value

if (a\[i\] \> slargest && a\[i\] \!= largest)  
slargest \= arr\[i\]

First pass is O(n) and we run one more loop which is also O(n) and then we have time complexity as O(2n)

The most optimal is like below  
largest \= a\[0\] and slargest \= \-1  
Then we traverse the array and check if the value is largest and if yes then we change the value  
Lets say a\[0\] \= 1  
So largest \=1 and next element is 2  
We check if 2 is larger than 1 yes it is then we update largest with 2 and then since 1 is not largest it can be slargest so we update the slargest as 1 and so on

