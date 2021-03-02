# Valid Palindrome
 - Leetcode #125
 
 
 ## Given a string `s`, determine if it is a palindrome, considering only alphanumeric characters and ignoring cases.
 
 **Example 1:**
 ```
 Input: s = "A man, a plan, a canal: Panama"
 Output: true
 Explanation: "amanaplanacanalpanama" is a palindrome.
 ```
 **Example 2:**
 ```
 Input: s = "race a car"
 Output: false
 Explanation: "raceacar" is not a palindrome.
 ```
 
 ## Solution
  - using pop(), pop(0) to check if left and right are equal
  
  ```python
  def isPalindrome(self, s: str) -> bool:
        s_list = []
        for char in s:
            if char.isalnum():
                s_list.append(char.lower())
                
        while len(s_list)>1 :
            if s_list.pop() != s_list.pop(0):
                return False
            
        return True
  ```
