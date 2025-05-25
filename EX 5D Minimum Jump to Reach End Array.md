# EX 5D Minimum Jump to Reach End Array
## DATE:
## AIM:
To write a python program for finding the minimum number of jumps needed to reach end of the array using Dynamic Programming.

## Algorithm:

1. Base Case : If start index l is equal to end index h, return 0 (already at the end).
2. If the value at current index arr[l] is 0, return infinity (cannot proceed further).
3. Recursive Case : Initialize min to infinity to track the minimum jumps.
4. For every index i reachable from l (i.e., i from l+1 to l + arr[l]), recursively find the minimum jumps needed from index i to h.
5. Update min if a shorter path is found (i.e., jumps + 1 < min).
6. Return Result : Return the minimum jumps required to reach the end from index l.

## Program:
```
Developed by: SAKTHIVEL R
Register Number: 212222100044
```

```py
def minJumps(arr, l, h):
    
    if (h == l):
        return 0
    if (arr[l] == 0):
        return float('inf')
    min = float('inf')
    for i in range(l + 1, h + 1):
        if (i < l + arr[l] + 1):
            jumps = minJumps(arr, i, h)
            if (jumps != float('inf') and
                       jumps + 1 < min):
                min = jumps + 1
 
    return min
    
    
arr = []
n = int(input()) 
for i in range(n):
    arr.append(int(input()))
print('Minimum number of jumps to reach','end is', minJumps(arr, 0, n-1))
 
```

## Output:

![23d](https://github.com/user-attachments/assets/c7870869-561d-44d4-91c6-72ac01e8c756)


## Result:

Thus the program was executed successfully for finding the minimum number of jumps to reach end.
