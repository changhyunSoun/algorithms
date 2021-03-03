# Group Anagrams
 - Leetcode #49


 ## 지문
 Given an array of strings `strs`, group the anagrams together.
 You can return the answer in any order.

 An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase,
 typically using all the original letters exactly once.

 
 **Example 1:**
 ```
 Input: strs = ["eat","tea","tan","ate","nat","bat"]
 Output: [["bat"],["nat","tan"],["ate","eat","tea"]]
 ```
 **Example 2:**
 ```
 Input: strs = [""]
 Output: [[""]]
 ```
 **Example 3:**
 ```
 Input: strs = ["a"]
 Output: [["a"]]
 ```

 
 ## 풀이
  - "".join(sorted()) 사용하여 같은 알파벳으로 이루어져있는 다른 단어 비교
  - {} 딕셔너리 key값을 정렬된 문자로, value는 [item1, item2] 그 문자들로 이루어진 서로 다른 단어를 리스트형태로 담기
  
  ```python
  def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
        result = []
        ana_dict = {}

        for item in strs:
            temp = "".join(sorted(item))
            if temp in ana_dict.keys():
                ana_dict[temp].append(item)
            else:
                ana_dict[temp] = [item]
            
        for key in ana_dict.keys():
            result.append(ana_dict[key])

        return result
  ```
