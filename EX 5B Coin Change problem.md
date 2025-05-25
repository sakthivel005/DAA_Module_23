# EX 5B Coin Change Problem
## DATE:
## AIM:
To compute the fewest number of coins that we need to make up the amount given.

## Algorithm:

1. Initialization : Create a dynamic programming (DP) array dp[] of size amount + 1, where dp[i] represents the minimum number of coins needed to make the amount i.
2. Initialize dp[0] = 0 since no coins are needed to make the amount 0, and set all other dp[i] to infinity (float('inf')), indicating that the amount i is not yet achievable.
3. Filling the DP Array : For each coin in the list of available coins, iterate over all amounts from the coin's value up to the target amount.
4. Update the DP array by setting dp[i] to the minimum of its current value and dp[i - coin] + 1 (i.e., using one more coin of the current denomination).
5. Result : After processing all coins, if dp[amount] is still infinity, return -1, indicating that it's not possible to form the amount with the given coins.
6. Otherwise, return dp[amount], which gives the minimum number of coins required.


## Program:
```
Developed by: SAKTHIVEL R
Register Number: 212222100044

```
```py
class Solution(object):
   def coinChange(self, coins, amount):
      
        dp = [float('inf')] * (amount + 1)
        dp[0]=0
        for coin in coins:
            for i in range(coin, amount + 1):
                dp[i] = min(dp[i], dp[i - coin] + 1)
        return dp[amount] if dp[amount]!=float('inf') else -1
      
      
ob1 = Solution()
n=int(input())
s=[]
amt=int(input())
for i in range(n):
    s.append(int(input()))


print(ob1.coinChange(s,amt))
```

## Output:

![23b](https://github.com/user-attachments/assets/57b612b4-c68d-4a1d-848c-549054809a50)

## Result:
Thus the program was executed successfully for finding the minimum number of coins required to make amount.
