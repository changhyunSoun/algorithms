# Most Common Word
 - Leetcode #819


 ## 지문
 Given a paragraph and a list of banned words, return the most frequent word that is not in the list of banned words.
 It is guaranteed there is at least one word that isn't banned, and that the answer is unique.

 Words in the list of banned words are given in lowercase, and free of punctuation. 
 Words in the paragraph are not case sensitive.  The answer is in lowercase.

 
 **Example :**
 ```
 Input: 
 paragraph = "Bob hit a ball, the hit BALL flew far after it was hit."
 banned = ["hit"]
 
 Output: "ball"
 
 Explanation: 
 "hit" occurs 3 times, but it is a banned word.
 "ball" occurs twice (and no other word does), so it is the most frequent non-banned word in the paragraph. 
 Note that words in the paragraph are not case sensitive,
 that punctuation is ignored (even if adjacent to words, such as "ball,"), 
 and that "hit" isn't the answer even though it occurs more because it is banned.
 ```

 
 ## 풀이
  - re.sub[r'[]', ] 정규표현식 사용하여 입력값 전처리 방법
  - collections.Counter() 사용하여 문자 빈도수 체크 방법
  - list comprehension 사용
  
  ```python
  def mostCommonWord(self, paragraph: str, banned: List[str]) -> str:
        paragraph = paragraph.lower()  # 대,소문자 구분하지 않으니 모두 소문자로 변경
        words = re.sub(r'[^\w]', ' ', paragraph) # 정규표현식으로 문자가 아닌 모든 문자를 공백으로 치환
               # re.sub('\W', ' ', paragraph) 와 같음
               
        words_list = words.split()
        words_list = [word for word in words_list if word not in banned] # banned에 해당하는 문자는 빼기
        
        counts = collections.Counter(words_list)
        return counts.most_common(1)[0][0]  # most_common(1) -> [('ball',3)] 이런식으로 리턴
  ```
