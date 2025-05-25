# EX 5C Kadane's Algorithm
## DATE:
## AIM:
To write a python program to find the maximum contiguous subarray.

## Algorithm:

1. Initialization : Start with two variables: max_till_now set to the first element of the array (as an initial maximum sum), and max_ending set to 0.
2. Iterate Through the Array : For each element in the array, add the element to max_ending.
3. If max_ending becomes negative, reset it to 0 (since we want to maximize the sum and a negative sum won't contribute to a higher value).
4. If max_ending is greater than max_till_now, update max_till_now to the value of max_ending.
5. Return the Result:After iterating through the array, return max_till_now, which holds the maximum sum of the contiguous subarray.

## Program:
```
Developed by: SAKTHIVEL R
Register Number: 212222100044
```
```py
def maxSubArraySum(a,size):
    
    max_till_now = a[0]
    max_ending = 0
    
    for i in range(0, size):
        max_ending = max_ending + a[i]
        if max_ending < 0:
            max_ending = 0
        
        
        elif (max_till_now < max_ending):
            max_till_now = max_ending
            
    return max_till_now
    
    
n=int(input())  
a =[] #[-2, -3, 4, -1, -2, 1, 5, -3]
for i in range(n):
    a.append(int(input()))
  
print("Maximum contiguous sum is", maxSubArraySum(a,n))

```

## Output:

![23c](https://github.com/user-attachments/assets/6ff87b7a-bc95-40d5-a3cc-75cc190afebc)


## Result:

Thus the program was executed successfully for finding the maximum contiguous sum of subarray..
