## 데이터 구조 Data Structure

---

- 메서드 method 를 활용
  
  - 메서드 는 클래스 내부에 정의한 함수
  - `데이터 구조.메서드()` 형태
  
  ```python
  # EX)
  List.append(10) # 리스트에 추가
  String.split() # 문자열을 쪼개기
  ```

---

- 문자열 String type
  
  - 모든 문자는 str (변경 불가 immutable)
  
  ```python
  word = 'ssafy'
  print(word) # ssafy
  print(id(word)) # 2177408668144
  word = 'test'
  print(word) # test
  print(id(word)) # 2177408959664
  # 변경이 된게 아니라, 변수에 다른 값을 저장한 것. 메모리 주소는 다름.
  # 문자는 immutable (변경 불가)
  
  s.find(x) # x 의 첫번째 위치를 반환 , 없으면 -1
  s.index(x) # x 의 첫번째 위치를 반환 , 오류 발생 (프로그램 멈춤)
  s.isalpha() # 알파벳 여부 - 유니코드 상 Letter (한국어 포함 / 비슷하게 생긴거 인정)
  s.isupper() # 대문자 여부
  s.islower() # 소문자 여부
  s.istitle() # 타이틀 형식 여부
  
  print('apple'.find('p')) # 1 
  print('apple'.find('k')) # -1
  
  print('apple'.index('p')) # 1 
  print('apple'.index('k')) # ValueError: substring not found
  
  print('abc'.isalpha()) # True
  print('ㄱㄴㄷ'.isalpha()) # True
  print('Ab'.isupper()) # False
  print('ab'.islower()) # True
  print('Title Title!'.istitle()) # True
  
  .isdecimal() .isdigit() .isnumeric()
  #  숫자         수..      수라고 보면 볼법한..?
  ```

```python
변경 메서드

s.replace(old,new[,count]) # 바꿀 대상 글자를 새로운 글자로 바꾸기
s.strip([chars]) # 공백이나 특정 문자 제거
s.split(sep=None, maxsplit=-1) # 공백이나 특정문자를 기준으로 분리
'separator'.join([itrrable]) # 반복가능한 요소들을 separator로 합쳐 문자열 반환
s.capitalize() # 가장 첫 글자 대문자로 변경
s.title() # 각 단어의 첫 글자 대문자
s.upper() # 모두 대문자
s.lower() # 모두 소문자
s.swapcase() # 대문자는 소문자로, 소문자는 대문자로

print('coone'.replace('o','a')) # caane
print('woooowoo'.replace('o','!',2)) # w!!oowoo

print('   와우!\\n'.strip()) # 와우!
print('   와우!\\n'.lstrip()) # 와우!
print('   와우!\\n'.rstrip()) #    와우!
print('안녕하세요????'.rstrip('?')) # 안녕하세요

print('a,b,c'.split(',')) # ['a', 'b', 'c']
print('a b c'.split()) # ['a', 'b', 'c'] 지정 없으면 공백
print('010-1234-1234'.split('-')) # ['010', '1234', '1234']

print('*'.join('ssafy')) # s*s*a*f*y
print(' '.join(['3','5','8','9'])) # 3 5 8 9

msg = 'hI! Everyone, I\\'m ssafy'
print(msg) # hI! Everyone, I'm ssafy
print(msg.capitalize()) # Hi! everyone, i'm ssafy
print(msg.title()) # Hi! Everyone, I'M Ssafy
print(msg.upper()) # HI! EVERYONE, I'M SSAFY
print(msg.lower()) # hi! everyone, i'm ssafy
print(msg.swapcase()) #Hi! eVERYONE, i'M SSAFY
```

---

- 리스트 List
  
  ```python
  L.append(x) # 리스트 마지막 항목에 x 추가
  L.insert(i,x) # 리스트 인덱스 i에 x 삽입
  L.remove(x) # 리스트 가장 왼쪽 항목 x 제거 , 항목 없으면 에러
  L.pop() # 리스트 가장 오른쪽 항목을 반환 후 제거
  L.pop(i) # 인덱스 i에 있는 항목을 반환 후 제거
  L.clear() # 항목 전부 삭제
  L.extend(m) # += 와 같은 기능
  L.index(x, start, end) # 리스트 항목 중 가장 왼쪽 항목 x의 인덱스 반환
  L.reverse() # 리스트 거꾸로 뒤집음 (정렬은 아님!!)
  L.sort() # 정렬(매개변수 이용 가능) / 원본 리스트를 정렬 / None 반환
  L.count(x) # x가 몇개 존재하는 지 갯수 반환
  
  cafe = ['star','tom','hollys']
  cafe.append('bana')
  print(cafe) # ['star', 'tom', 'hollys', 'bana']
  cafe.insert(0,'start') # 리스트 길이보다 큰 인덱스를 넣을때는 맨 끝으로 삽입됨
  print(cafe) # ['start', 'star', 'tom', 'hollys', 'bana']
  cafe.extend(['coffee'])
  print(cafe) # ['start', 'star', 'tom', 'hollys', 'bana', 'coffee']
  cafe.extend('cup') # 문자열은 글자로 추가 됨
  print(cafe) # ['start', 'star', 'tom', 'hollys', 'bana', 'coffee', 'c', 'u', 'p']
  
  num = [1,2,3,'hi']
  num.remove('hi')
  print(num) # [1, 2, 3]
  word = num.pop()
  print(word) # 3
  print(num) # [1, 2]
  
  num = [1,2,3,1,1,1,2,2]
  print(num.count(1)) # 4
  print(num.count(100)) # 0
  
  **# sort 와 sorted 차이**
  num = [3,2,5,7]
  result = num.sort()
  print(num, result) # [2, 3, 5, 7] None
  
  num = [3,2,6,8]
  result = sorted(num)
  print(num, result) # [3, 2, 6, 8] [2, 3, 6, 8]
  
  num = [3,2,5,1]
  result = num.reverse()
  print(num, result) # [1, 5, 2, 3] None
  ```

---

- 튜플 Tuple
  
  - 변경 불가 immutable
  - 값에 영향을 미치지 않는 메서드만 지원
  
  ```python
  a = (1,2,3,5,1)
  a[0] = 5 
  # TypeError: 'tuple' object does not support item assignment
  
  day_name = ('월','화','수','목','금')
  print(type(day_name)) # <class 'tuple'>
  print(day_name[-3]) # 수
  print(day_name * 2) # ('월', '화', '수', '목', '금', '월', '화', '수', '목', '금')
  print(id(day_name)) # 1932687396272
  day_name+= False, True
  print(day_name) # ('월', '화', '수', '목', '금', False, True)
  print(id(day_name)) # 1932688775584
  ```

---

- 연산자 Operator
  
  - 멤버십 연산자 Membership Operator
  - 포함 여부 확인
    - `in` `not in` ( 리스트, 튜플, 문자열, range )
  - 시퀀스형 연산자 Sequence Type Operator ( 리스트, 튜플, 문자열 )
    - 산술 연산자 `+`
      - 시퀀스 간의 연결 / 연쇄
    - 반복 연산자 `*`
      - 시퀀스를 반복
  
  ```python
  print('a' in 'apple') # True
  print('hi' in 'hi I am ssafy') # True
  print('서순' in ['서순', '요까일엇무', '기러기']) # True
  
  산술 연산자
  [1,2] + ['a']
  # [1,2,'a']
  (1,2) + ('a',)
  # (1,2,'a')
  '12' + 'b'
  # '12b'
  
  반복 연산자
  [0] * 8
  # [0,0,0,0,0,0,0,0]
  (1,2) * 3
  # (1,2,1,2,1,2)
  'hi' * 3
  # 'hihihi'
  ```

---

- 셋 Set
  
  ```python
  s.copy() # 얕은 복사본 반환
  s.add(x) # x 가 셋 s에 없다면 추가
  s.pop() # 셋 s에서 랜덤하게 항목 반환 후 제거 , 비어있을 경우 에러
  s.remove(x) # x 를 s에서 삭제 , 존재하지 않을 경우 에러
  s.discard(x) # x 를 s에서 삭제, No 에러
  s.update(t) # 셋 t에 있는 항목 중 셋 s에 없는 항목 추가
  s.clear() # 모든 항목 제거
  s.isdisjoint(t) # s와 t가 서로 같은 항목이 없는 경우, True (서로소)
  s.isssubset(t) # s가 t의 하위 셋 경우, True (t안에 s)
  s.issuperset(t) # s가 t의 상위 셋 경우, True (s안에 t)
  
  a = {'사과', '바나나', '수박'}
  a.add('딸기')
  print(a) # {'딸기', '사과', '수박', '바나나'} / 순서 랜덤 -> **셋** 이니까!
  a.update({'딸기','바나나','참외'})
  print(a) # {'딸기', '참외', '수박', '바나나', '사과'} / 겹치는거 빼고!
  a.remove('사과')
  print(a) # {'참외', '딸기', '수박', '바나나'}
  a.clear()
  print(a) # set()
  
  a = {'사과', '바나나', '수박'}
  b = {'포도','망고'}
  c = {'사과','포도','망고','수박','바나나'}
  print(a.isdisjoint(b)) # True -> a와 b는 서로소
  print(b.issubset(c)) # True -> b가 c의 하위 셋
  print(a.issuperset(c)) # False -> a가 c의 상위 셋이 아님 !!
  ```

---

- 딕셔너리 Dictionary
  
  ```python
  d.clear() # 모든 항목 제거
  d.copy() # 딕셔너리 d 의 얕은 복사본 반환
  d.keys() # 딕셔너리 d의 모든 키를 담은 뷰를 반환
  d.values() # 딕셔너리 d의 모든 밸류를 담은 뷰를 반환
  d.items() # 딕셔너리 d의 모든 키- 밸류 쌍 값을 담은 뷰를 반환
  d.get(k) # 키 k를 통해 value 를 가져옴 / 에러 X / 디폴트 설정 가능 (기본:None)
  d.get(k,v) # 키 k를 통해 value 를 가져옴 / 없을 경우 v 반환
  d.pop(k) # 키가 딕셔너리에 있으면 반환 후 제거 / 디폴트 없으면 에러
  d.pop(k,v) # 키가 딕셔너리에 있으면 반환 후 제거 / 없으면 v 반환
  d.update([other]) # 딕셔너리 d의 값을 매핑하여 업데이트 
  
  my_dict = {'apple': '사과', 'banana':'바나나'}
  data = my_dict.pop('apple')
  print(data, my_dict) # 사과 {'banana': '바나나'}
  data = my_dict.pop('apple',0)
  print(data) # 0
  
  my_dict = {'apple': '사', 'banana':'바나나'}
  my_dict.update(apple = '사과')
  print(my_dict) # {'apple': '사과', 'banana': '바나나'}
  
  my_dict = {'apple': '사과', 'banana':'바나나'}
  
  for value in my_dict.values():
      print(value) 
  # 사과
  # 바나나
  for key in my_dict.keys():
      print(key) 
  # apple
  # banana
  for key,value in my_dict.items():
      print(f'key:{key} / value:{value}')
  # key:apple / value:사과
  # key:banana / value:바나나
  ```

---

### 얕은 복사와 깊은 복사 Shallow Copy & Deep Copy

---

- 할당 assignment
  
  - 대입 연산자 `=`
    - 해당 객체에 대한 객체 참조를 복사
  
  ```python
  original_list = [1,2,3]
  copy_list = original_list
  print(original_list, copy_list) # [1, 2, 3] [1, 2, 3]
  
  copy_list[0] = 'hello'
  print(original_list, copy_list) # ['hello', 2, 3] ['hello', 2, 3]
  ```

- 얕은 복사 shallow copy
  
  - slice 연산자 활용
  - 같은 원소를 가진 리스트지만 연산 된 결과를 복사
  
  ```python
  original_list = [1,2,3]
  copy_list = original_list[:]
  print(original_list, copy_list) # [1, 2, 3] [1, 2, 3]
  
  copy_list[0] = 'hello'
  print(original_list, copy_list) # [1, 2, 3] ['hello', 2, 3]
  ```
  
  - 주의 사항
    - 1차원 리스트에서만 가능
    - 복사하는 리스트의 원소가 주소를 참조하는 경우
  
  ```python
  # 아래의 예시는 2차원 리스트 - 얕은 복사 되지 않음!!
  
  a = [1,2,['a','b']]
  b = a[:]
  print(a,b) # [1, 2, ['a', 'b']] [1, 2, ['a', 'b']]
  b[2][0] = 0
  print(a,b) # [1, 2, [0, 'b']] [1, 2, [0, 'b']]
  ```

- 깊은 복사 deep copy
  
  ```python
  import copy
  
  a = [[1,2,3],[4,5,6],[7,8,9]]
  b = copy.deepcopy(a)
  print(a, b) 
  # [[1, 2, 3], [4, 5, 6], [7, 8, 9]] [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
  
  b[0][2] = 'hello'
  print(a, b) 
  # [[1, 2, 3], [4, 5, 6], [7, 8, 9]] [[1, 2, 'hello'], [4, 5, 6], [7, 8, 9]]
  ```
