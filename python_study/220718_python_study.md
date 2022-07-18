## 변수 Variable

---

- 데이터를 담는 상자

- 복잡한 값들을 쉽게 사용할 수 있음 (추상화)

- 동일 변수에 다른 데이터를 언제든 할당 할 수 있기 때문에, ‘변수’라고 불림

- 변수의 할당
  
  ```python
  americano_price = 2000
  cookie_price = 2000
  
  americano_price = cookie_price = 2000
  # 동일 값 한번에 입력 가능
  ```

- 변수 값 바꾸기
  
  ```python
  x, y = 10, 20
  tmp = x
  # 다른 변수를 생성하여 위치 옮기기 / 임시 변수
  x = y
  y = tmp
  print(x, y)
  # >>> 20, 10
  
  # 파이썬에서 가능한 변수 스왑
  x, y = 10, 20
  x, y = y, x 
  print(x, y)
  # >>> 20, 10
  ```

---

## 식별자

---

- 변수 이름 규칙
  
  - 영문 알파벳 , 언더스코어( _ ) , 숫자로 구성
  - 첫 글자 숫자 불가능
  - 길이 제한 없고, 대소문자 구별
  - `예약어` 사용 불가
  
  ```python
  import keyword
  print(keyword.kwlist)
  # 확인 가능
  
  ['False', 'None', 'True', '__peg_parser__', 'and', 'as', 'assert', 
  'async', 'await', 'break', 'class', 'continue', 'def', 'del', 'elif', 
  'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 
  'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 
  'try', 'while', 'with', 'yield']
  ```

---

## 연산자

---

- 산술 연산자 Arithmetic Operator
  - - 더하기 - 빼기
  - - 곱하기 / 나누기
  - // 몫
  - ** 거듭 제곱
- 연산자 우선순위
  - 기본적인 수학에서 우선순위와 같음

---

## 자료형 Datatype

---

- 사용할 수 있는 데이터의 종류

- 수치형 Numeric
  
  - `int` - 정수 자료형
    
    - 여러 진수로 표현 가능 `2진수(binary)` `8진수(octal)` `16진수(hexadecimal)`
  
  - `float` - 실수 자료형
    
    - 부동(float) 소수점 주의 → 임의의 작은 수 활용하여 해결
    
    ```python
    Ex)
    print(3.2 - 3.1)
    # >>> 0.10000000000000009
    print(1.2 - 1.1)
    # >>> 0.09999999999999987
    ```

- 문자열 String
  
  - 모든 문자는 str 타입
  
  - `''` , `""` 로 표기
    
    - 동일한 문장 부호 활용
    - 소스코드 내에서 하나의 문장 부호 선택 유지
  
  - 중첩 따옴표
    
    - 문자열 안에 `''` 를 쓰고 싶다면 전체를 `""` 로 감싸기 (반대의 경우도 동일)
  
  - 삼중 따옴표 `''' '''`
    
    - 여러 줄을 나눠 입력 할 때
  
  - Escape Sequence
    
    - 역슬래시 `\\`
    
    ```python
    \\n 줄바꿈 \\t 탭 \\r 캐리지 리턴 \\0 널(Null) 
    \\\\ \\   \\' '   \\" "
    
    print('철수 \\'안녕\\' ')
    print('이 다음은 엔터. \\n 그리고 탭\\t탭')
    # >>>
    철수 '안녕' 
    이 다음은 엔터. 
     그리고 탭      탭
    
    print('"안녕"하고..\\n''가다가 생각했다.\\n\\'아, 이거 준다는걸 깜빡했네\\'')
    # >>>
    "안녕"하고..
    가다가 생각했다.
    '아, 이거 준다는걸 깜빡했네'
    
    # * 로 직사각형 만들기 
    n = 3
    m = 5
    print((('*' * n) + '\\n') * m)
    # >>>
    ***
    ***
    ***
    ***
    ***
    ```
  
  - 연산
    
    ```python
    print('Hello' + 'World')
    # HelloWorld
    print('Python' * 3)
    # PythonPythonPython
    
    name = 'kim'
    score = 4.5
    print('Hello, %s' %name)
    # Hello, kim
    print('Hello, %d' %score)
    # Hello, 4
    print('Hello, %f' %score)
    #Hello, 4.500000
    
    print('Hello, {}! 성적은 {}'.format(name,score))
    # Hello, kim! 성적은 4.5
    
    print(f'Hello, {name}! 성적은 {score}')
    # Hello, kim! 성적은 4.5
    ```
    
    ```python
    import datetime
    today = datetime.datetime.now()
    print(today)
    # 2022-07-18 11:27:38.545788
    print(f'오늘은 {today:%y}년 {today:%m}월 {today:%d}일')
    # 오늘은 22년 07월 18일
    
    pi = 3.141592
    print(f'원주율은 {pi:.3}. 반지름이 2일 때 원의 넓이는 {pi*2*2}')
    # 원주율은 3.14. 반지름이 2일 때 원의 넓이는 12.566368
    ```

- 불린형 Boolean
  
  - 논리 자료형 `True` `False`
  - 비교 / 논리 연산에서 활용

- None
  
  - 값이 없음을 표현
  - 반환 값이 없는 함수에서 사용하기도 함

- 비교 연산자
  
  - 등호 부등호
  - 주로 조건문에 사용 / 결과는 True False
  - `<` `<=` `>` `>=` `==` `!=` `is` `is not`

- 논리 연산자
  
  - 모든 조건을 만족 `and`
  
  - 여러 조건 중 하나만 만족 `or`
  
  - True 를 False 로, False 를 True 로 `not`
  
  - 일반적으로 비교 연산자와 함께 사용
  
  - `주의할 점` / `not` 연산자
    
    - `Falsy` : False는 아니지만 False 취급 → `0` `0,0` `()` `[]` `{}` `None` `''` `""`
    - 논리 연산자도 우선순위 존재 → `not` `and` `or` 순서
    
    ```python
    print(not True) # False
    print(not 0) # True
    print(not 'hi') # False
    print(not True and False or not False) # True
    print(((not True)and False) or (not False)) # True
    ```
  
  - 단축 평가
    
    - 결과가 확실한 경우 두번째 값은 확인하지 않고 첫번째 값 반환
    - `and` 첫번째 값 False → 첫번째 값
    - `or` 첫번째 값 True → 첫번째 값
    
    ```python
    print(3 and 5) # 5 -> 두번째 값이 False인지 체크
    print(3 and 0) # 0
    print(0 and 3) # 0 -> 이미 0이 False 라서, 첫번째 값으로 반환
    
    print(5 or 3) # 5
    print(3 or 0) # 3
    print(0 or 3) # 3 -> 둘 중 하나라도 True 일 수 있으니, 두번째 값 확인 후 반환 
    ```

---

## 컨테이너

---

- 여러 개의 데이터를 담을 수 있는 객체
- 서로 다른 자료형을 저장 가능
- `Ordered(순서가 있는 데이터)` `Unordered(순서가 없는 데이터)` (순서가 있다 ≠ 정렬되어 있다)

---

### 시퀀스형 컨테이너

---

- 리스트
  
  - 여러 개의 값을 순서가 있는 구조 (파이썬은 모든 자료형 가능, 리스트에 리스트 넣기도 가능)
  - 0번째부터 시작
  - `[ ]` `list()` 를 통해 생성
  - 순서가 있는 시퀀스 → 인덱스를 통해 접근 가능
  
  ```python
  my_list = []
  another_list = list()
  print(type(my_list)) # <class 'list'>
  
  list_a = [1,2,3]
  list_b = ['Life','is','too','short']
  list_c = [1,2,3,'python',['리스트','안에','리스트']]
  print(list_c[0]) # 1
  list_b[3] = 'long'
  print(list_b) # ['Life', 'is', 'too', 'long']
  
  boxes = ['A','B',['apple','banana','cherry']]
  print(len(boxes)) # 3
  print(boxes[2]) # ['apple','banana','cherry']
  print(boxes[2][-1]) # cherry
  print(boxes[-1][1][0]) # b
  ```

- 튜플
  
  - 불변 자료형 (여러 개의 값을 순서가 있는 구조)
  - 리스트와 다른 점 → 생성 후, 담고 있는 값 변경 불가
  - `()` `tuple()` 를 통해 생성
  - 단일 항목이라면, 값 뒤에 `,` 를 붙여야 함
  - 복수 항목은 쉼표가 없어도 되지만 넣는 것을 권장
  - 튜플 대입 Tuple assignment
    - 우변의 값을 좌변의 변수에 한 번에 할당하는 과정
  
  ```python
  a = (1,2,3,1)
  print(a) # (1,2,3,1)
  print(type(a)) # <class 'tuple'> 
  b = 1,2,3 # 이렇게도 가능
  print(b) # (1,2,3)
  print(type(b)) # <class 'tuple'> 
  tuple_a = (1,)
  print(tuple_a) # (1,)
  print(type(tuple_a)) # <class 'tuple'> 
  ```

- Range
  
  - 숫자의 시퀀스를 나타내기 위해 사용
  - 주로 반복문과 활용
  
  ```python
  print(range(4)) # range(0,4)
  print(list(range(4))) # [0,1,2,3] -> 기본형
  print(list(range(1,5))) # [1,2,3,4] -> 범위 지정
  print(list(range(1,5,2))) # [1,3] -> 범위 스텝 지정 (1부터 5-1까지 2만큼 증가시키면서)
  
  print(list(range(6,1,-1))) # [6,5,4,3,2] -> 6번째부터 1+1까지 -1 하면서
  print(list(range(6,1,-2))) # [6,4,2] -> 6번째부터 1+1까지 -2 하면서
  print(list(range(6,1,1))) # [] -> 66번째부터 1+1까지 +1 하면서? 없음.
  ```

- 슬라이싱
  
  - 인덱스와 콜론을 이용하여 문자열의 특정 부분만 잘라낼 수 있음
  
  ```python
  # 리스트
  print([1,2,3,5][1:4]) # [2,3,5]
  print([1,2,3,5][0:4:2]) # [1,3] -> 2칸 간격
  
  # 튜플
  print((1,2,3)[:2]) # (1,2)
  print((1,2,3,5)[0:4:2]) # (1,3)
  
  # range
  print(range(10)[5:8]) # range(5, 8)
  print(range(10)[1:5:3]) # range(1, 5, 3)
  
  # 문자열
  print('abcd'[2:4]) # cd
  print('abcdefg'[1:3:2]) # b
  
  s = 'abcdefghi'
  print(s[::]) # 'abcdefghi'
  print(s[::-1]) # 'ihgfedcba'
  ```

---

### 비 시퀀스형 컨테이너

---

- 셋 set
  
  - 수학에서의 집합 **( 합집합, 차집합, 교집합 )**
  - 중복 X , 순서 X
  - 담고 있는 요소 삽입, 변경, 삭제 가능 → 가변 자료형
  - `{}` `set()` 을 통해 생성 **( 빈 중괄호 불가능 )**
  - 실행 할 때 반환 값 순서가 변경 되는 경우 있으니, 순서 중요? NO set
  
  ```python
  print({1,2,3,1,2}) # {1,2,3} -> 중복 X
  
  blank = {}
  print(type(blank)) # <class 'dict'>
  blank_set = set()
  print(type(blank_set)) # <class 'set'>
  
  A_set = {1,2,3,4}
  B_set = {1,2,3,'Hello',(1,2,3)}
  
  print(A_set | B_set) # {1,2,3,4,(1,2,3),'Hello'} 합집합
  print(A_set & B_set) # {1,2,3} 교집합
  print(B_set - A_set) # {(1,2,3),'Hello'} 차집합
  print(A_set ^ B_set) # {'Hello',4,(1,2,3)} 대칭차집합 = 합집합 - 교집합
  ```

- 딕셔너리
  
  - `키 key` `밸류 value` 쌍으로 이뤄진 자료형 (3.7부터 ordered)
  - `key` 는 변경 불가능한 데이터 **immutable**
  - `values` 는 어떠한 형태든 관계 없음
  - `{}` `dict()` 를 통해 생성
  - `key` 를 통해 `value` 에 접근
  
  ```python
  dict_a = {'a':'apple','b':'banana','list':[1,2,3]}
  print(dict_a) # {'a':'apple','b':'banana','list':[1,2,3]}
  print(dict_a['list']) # [1,2,3]
  
  dict_b = dict(a:'apple',b:'banana',list:[1,2,3])
  print(dict_b) # {'a':'apple','b':'banana','list':[1,2,3]}
  
  dict_c = {'lee':85, 'kim':80, 'jun':100}
  dict_c['phang'] = 90
  list_c = list(dict_c.keys())
  print(list_c) # ['lee', 'kim', 'jun']
  ```

---

## 형 변환 Typecasting

---

- 암시적 형 변환 - **implict**
  
  - 파이썬이 내부적으로, 자동, 사용자 의도 X
  - `bool` `Numeric type (int, float)`
  
  ```python
  print(True + 3) # 4 -> True = 1 로 자동 변경
  print(3 + 5.0) # 8.0 -> int와 float의 덧셈을 float로 자동 변경
  ```

- 명시적 형 변환 - **explicit**
  
  - 개발자가, 특정 함수를 활용, 의도적
  - `str, float` → `int` (형식에 맞는 문자열만 가능)
  - `str, int` → `float` (형식에 맞는 문자열만 가능)
  - `int, float, list, tuple, dict` → `str`
  
  ```python
  print('3' + 4) # 에러 -> str 과 int 더하기 불가
  print(int('3.5') + 5) # 에러 -> '3.5'를 int로 변환 불가
  print(int('3') + 4) # 7
  print('3' + str(4)) # 34 -> 둘 다 str로서 붙은 34 인 것
  
  print('3.5' + 3.5) # 에러 -> str 과 float 더하기 불가
  print(float('3/4') + 5.3) # 에러 -> '3/4' str가 float 형식이 아니라 불가
  print(float'3')) # 3.0
  ```

---
