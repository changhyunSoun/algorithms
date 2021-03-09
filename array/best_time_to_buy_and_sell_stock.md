# Best Time to Buy and Sell Stock
 - Leetcode #121


## 지문
You are given an array `prices` where `prices[i]` is the price of a given stock on the `i^th` day.

You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.

Return the maximum profit you can achieve from this transaction. If you cannot achieve any profit, return `0`.
 
 **예제 1:**
 ```
 Input: prices = [7,1,5,3,6,4]
 Output: 5
 Explanation: Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6-1 = 5.
 Note that buying on day 2 and selling on day 1 is not allowed because you must buy before you sell.
 ```
 **예제 2:**
 ```
 IInput: prices = [7,6,4,3,1]
 Output: 0
 Explanation: In this case, no transactions are done and the max profit = 0.
 ```
 
 ## 풀이
  - min() / max() 로  최소 가격과 최대 이익을 지속적으로 갱신하여 비교하는 방법
  
  ```python
  def maxProfit(self, prices: List[int]) -> int:
        profit = 0
        min_price = sys.maxsize    # min() 비교를 위해 초기 price를 시스템상 최대값 선언

        for price in prices:
            min_price = min(min_price, price)       # min_price를 최소 가격으로 갱신
            profit = max(profit, price - min_price) # 판매 이익은 최대 값으로 갱신
        
        return profit
  ```
