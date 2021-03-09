# Valid Palindrome
 - Leetcode #125
 
 
 ## 지문
 Given a string `s`, determine if it is a palindrome, considering only alphanumeric characters and ignoring cases.
 
 **예제 1:**
 ```
 Input: s = "A man, a plan, a canal: Panama"
 Output: true
 Explanation: "amanaplanacanalpanama" is a palindrome.
 ```
 **예제 2:**
 ```
 Input: s = "race a car"
 Output: false
 Explanation: "raceacar" is not a palindrome.
 ```
 
 ## 풀이
  - pop() , pop(0) 을 이용하여 좌측. 우측 문자가 같은지 확인하는 방법
  
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
