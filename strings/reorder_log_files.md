# Reorder Log Files
 - Leetcode #937


 
You are given an array of `logs`. Each log is a space-delimited string of words, where the first word is the **identifier**.

There are two types of logs:

- **Letter-logs:** All words (except the identifier) consist of lowercase English letters.
- **Digit-logs:** All words (except the identifier) consist of digits.

Reorder these logs so that:

1. The **letter-logs** come before all **digit-logs**.
2. The **letter-logs** are sorted lexicographically by their contents. If their contents are the same, then sort them lexicographically by their identifiers.
3. The **digit-logs** maintain their relative ordering.
Return the final order of the logs. 

 
 **Example 1:**
 ```
 Input: logs = ["dig1 8 1 5 1","let1 art can","dig2 3 6","let2 own kit dig","let3 art zero"]
 Output: ["let1 art can","let3 art zero","let2 own kit dig","dig1 8 1 5 1","dig2 3 6"]
 Explanation:
 The letter-log contents are all different, so their ordering is "art can", "art zero", "own kit dig".
 The digit-logs have a relative order of "dig1 8 1 5 1", "dig2 3 6".
 ```
 **Example 2:**
 ```
 Input: logs = ["a1 9 2 3 1","g1 act car","zo4 4 7","ab1 off key dog","a8 act zoo"]
 Output: ["g1 act car","a8 act zoo","ab1 off key dog","a1 9 2 3 1","zo4 4 7"]
 ```
 
 ## 풀이
  - sort(key = lambda x: )   lambda를 사용하여 정렬 기준에 따라 정렬하는 방법
  
  ```python
  def reorderLogFiles(self, logs: List[str]) -> List[str]:
        letters = []  # 문자 log 
        digits = []   # 숫자 ㅣog
        
        for log in logs:
            if log.split()[1].isalpha() == True:
                letters.append(log)
            else:
                digits.append(log)
        # 문자 log는 문제 기준에 맞춰 재정렬
        letters.sort(key = lambda x: (x.split()[1:], x.split()[0]))
        
        return letters + digits
  ```
