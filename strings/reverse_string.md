# Reverse String
 - Leetcode #344
 
 
 ## Write a function that reverses a string. The input string is given as an array of characters `char[]`. 
 
 **Example 1:**
 ```
 Input: ["h","e","l","l","o"]
 Output: ["o","l","l","e","h"]
 ```
 **Example 2:**
 ```
 Input: ["H","a","n","n","a","h"]
 Output: ["h","a","n","n","a","H"]
 ```
 
 ## 풀이 #1
  - left, right 변수로 인덱스에 접근하여 좌측과 우측 자리를 교환하는 방법
  
  ```python
  def reverseString(self, s: List[str]) -> None:
        """
        Do not return anything, modify s in-place instead.
        """
        left = 0             #index
        right = len(s)-1     #index
        while right>left:
            temp = s[left]
            s[left] = s[right]
            s[right] = temp
            left += 1
            right -= 1
  ```
  
  ## 풀이 #2
   - reverse()를 사용한 간편한 방법
   
   ```python
   def reverseString(self, s: List[str]) -> None:
        s.reverse()
   ```
