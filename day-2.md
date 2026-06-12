# Day 2

Problem: Best Time to Buy and Sell Stock
LeetCode: https://leetcode.com/problems/best-time-to-buy-and-sell-stock/description/

```js
function maxProfit(prices) {
  let minPrice = Infinity;
  let maxProfit = 0;
  for (let i = 0; i < prices.length; i++) {
    if (prices[i] < minPrice) {
      minPrice = prices[i];
    } else if (prices[i] - minPrice > maxProfit) {
      maxProfit = prices[i] - minPrice;
    }
  }
  return maxProfit;
}
```

Input: an array of strings (lol)

Output: an integer representing the max profit

Algorithm:
Single pass with two trackers. Keep a running minPrice seen so far. At each price, either it's a new minimum, or check if selling today beats the current maxProfit. No need to look back because the best buy point is always the lowest price seen before the current day.

Time: O(n) | Space: O(1)

Python Solution:

```py
def maxProfit(prices):
    min_price = float('inf')
    max_profit = 0
    for price in prices:
        if price < min_price:
            min_price = price
        elif price - min_price > max_profit:
            max_profit = price - min_price
    return max_profit
```
