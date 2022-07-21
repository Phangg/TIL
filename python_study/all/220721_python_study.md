- print
  
  ```jsx
  print('첫번째 문장')
  print('두번째 문장', end='_')
  print('세번째 문장', '네번째 문장')
  print('다섯번째 문장', '마지막 문장', sep='/', end='끝!')
  
  # 첫번째 문장
  # 두번째 문장_세번째 문장 네번째 문장
  # 다섯번째 문장/마지막 문장끝!
  ```

---

## 제어문 control statement

---

- 순서도 flowchart로 표현이 가능
- 특정 상황에 따라 코드를 선택적으로 실행(분기/조건)하거나 계속하여 실행(반복)하는 제어 필요

---

### **조건문**

- 참 / 거짓을 판단할 수 있는 조건식과 함께 사용
  
  ![조건문.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/43b990a8-d850-4414-9a35-94366ddce739/%EC%A1%B0%EA%B1%B4%EB%AC%B8.png)
  
  ```python
  if 조건 == True:
      실행코드(들여쓰기)
  else:
      실행코드(들여쓰기)
  
  a = 5
  if a > 5 :
      print('5 초과')
  else:
      print('5 이하')
  # 5 이하
  
  num = int(input('숫자 입력'))
  if num % 2 == 0:
      print('짝수')
  else:
      print('홀수')
  # input : 3    output : 홀수
  ```

- 복수 조건문
  
  ```python
  if 조건:
      실행 코드
  elif 조건:
      실행 코드
  elif 조건:
      실행 코드
  else:
      실행 코드
  
  dust = 80
  if dust > 150:
      print('매우 나쁨')
  elif dust > 80:
      print('나쁨')
  elif dust > 30:
      print('보통')
  else:
      print('좋음')
  print('미세먼지 확인 완료')
  # 보통
  # 미세먼지 확인 완료
  ```

- 중첩 조건문
  
  ```python
  if 조건:
      실행 코드
      if 조건:
          실행코드
  else:
      실행코드
  
  dust = 500
  if dust > 150:
      print('매우 나쁨')
      if dust > 300:
          print('실외 활동 자제하세요')
  elif dust > 80:
      print('나쁨')
  elif dust > 30:
      print('보통')
  elif dust >= 0:
      print('좋음')
  else:
      print('값이 잘못 되었습니다')
  # 매우 나쁨
  # 실외 활동을 자제하세요
  ```

- 조건 표현식 Conditional Expression
  
  - `삼항연산자 Ternary Operator` 로 부르기도 함
  
  ```python
  true 경우 값 if 조건 else false 경우 값
  
  value = num if num >= 0 else -num
  # value에 절대값 저장 코드
  
  num = 3
  result = '홀수' if num % 2 else '짝수'
  print(result)
  # 홀수
  
  num = -5
  if num >= 0:
          value = num
  else:
          value = 0
  print(value)
  #위 아래 서로 같은 출력 값을 갖는 코드
  num = -5
  value = num if num >= 0 else 0
  print(value)
  ```

---

### **반복문**

- 특정 조건 만족할 때까지 반복

- `while`
  
  - 종료 조건에 해당하는 코드를 통해 반복문 종료

- `for`
  
  - 반복 가능한 객체를 모두 순화하면 종료

- `반복 제어`
  
  - break , continue , for-else
  
  ![반복문.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/7cd1fc6b-df22-4c2b-9fb9-e507f89af61b/%EB%B0%98%EB%B3%B5%EB%AC%B8.png)

- **while**
  
  - 조건식 참인 경우 코드 반복 실행
  - 무한 루프 되지 않도록 종료 조건 반드시 필요
  
  ```python
  while 조건: # 조건이 참인 동안
      코드 실행 # 맞다면 코드 실행 -> 다시 위로 가서 조건 체크
  
  a = 0
  while a < 4: # a 가 4보다 작은 동안
      print(a)
      a += 1 # a = a + 1
  print('끝!')
  # 0 
  # 1
  # 2
  # 3
  # 끝!
  
  num = int(input()) # input : 185
  while num > 0:
      d,m = divmod(num, 10)
      num = d
      print(m)
  # 5
  # 8
  # 1
  ```
  
  - 복합 연산자 `+=`

- **for**
  
  - 시퀀스(string, tuple, list, range)를 포함한 순화 가능한 객체의 요소를 모두 순환
  - 종료 조건 필요하지 않음
  - iterable
    - 순회할 수 있는 자료형 (string, list, dict, tuple, set 등)
    - 순회형 함수(range, enumerate)
  
  ```python
  for 변수명 in iterable:
      실행 코드
  
  for fruit in ['apple','banana','mango']
      print(fruit)
  print('끝')
  # apple
  # banana
  # mango
  # 끝
  
  chars = input() # input : happy
  for char in chars:
      print(char)
  # h
  # a
  # p
  # p
  # y
  
  grades = {'john':80, 'eric':90}
  for student in grades:
      print(student) # 딕셔너리 - 기본적으로 키 값을 순회하기에 키값 추출
  # john
  # eric 
  
  grades = {'john':80, 'eric':90}
  for student in grades:
      print(student, grades[student]) # + 밸류 값 추출
  # john 80
  # eric 90
  
  grades = {'john':80, 'eric':90}
  for student,grade in grades.items(): # items() 가 (키,밸류) 튜플 구성
      print(student, grade)
  # john 80
  # eric 90
  
  # 0. dictionary 순회 (key 활용)
  for key in dict:
      print(key)
      print(dict[key])
  
  # 1. `.keys()` 활용
  for key in dict.keys():
      print(key)
      print(dict[key])
  
  # 2. `.values()` 활용
  # 이 경우 key는 출력할 수 없음
  for val in dict.values():
      print(val)
  
  # 3. `.items()` 활용
  for key, val in dict.items():
      print(key, val)
  ```

- **enumerate 순회**
  
  ![enumerate.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e99d2194-9a8a-40d2-a211-831891b0de4f/enumerate.png)
  
  - enumerate()
  - (index, value) 형태의 튜플로 구성된 열거 객체 반환
  
  ```python
  members = ['민수','영희','철수']
  enumerate(members)
  print(list(enumerate(members))) # [(0,'민수'), (1,'영희'),(2,'철수')]
  print(list(enumerate(members, start = 1)))
  # [(1,'민수'), (2,'영희'),(3,'철수')]
  print(list(enumerate(members))[0]) # (0, '민수')
  print(type(list(enumerate(members))[0])) # <class 'tuple'>
  
  lst = ['a','b','c']
  print({x+1:lst[x] for x in range(len(lst))}) # {1: 'a', 2: 'b', 3: 'c'}
  print({idx,value for idx,value in enumerate(lst,1)}) # {1: 'a', 2: 'b', 3: 'c'}
  ```

- list comprehension
  
  ```python
  [코드 for 변수 in iterable]
  
  [코드 for 변수 in iterable if 조건식]
  
  cubic_list = []
  for number in range(1,4):
      cubic_list.append(number ** 3)
  print(cubic_list)
  # [1,8,27]
  
  cubic_list = [number ** 3 for number in range(1,4)]
  print(cubic_list)
  # [1,8,27]
  ```

- dictionary comprehension
  
  ```python
  {key:value for 변수 in iterable}
  
  {key:value for 변수 in iterable if 조건식}
  
  cubic_dict = {}
  for number in range(1,4):
      cubic_dict[number] = number ** 3 # cubic_dict[1] = 1 -> {1: 1}
  print(cubic_dict)
  # {1: 1, 2: 8, 3: 27}
  
  cubic_dict = {number:number **3 for number in range(1,4)]
  print(cubic_dict)
  # {1: 1, 2: 8, 3: 27}
  ```

- **반복문 제어**
  
  ![반복문 제어.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/7e27377a-f4ae-4f2a-b3f0-ca372250716f/%EB%B0%98%EB%B3%B5%EB%AC%B8_%EC%A0%9C%EC%96%B4.png)
  
  - break
    - 반복문 종료
  
  ```python
  n = 0
  while True: # 계속해서 반복해라
      if n == 3: 
          break # n 이 3이 되면 끝내라
      print(n)
      n += 1
  # 0
  # 1
  # 2
  
  for i in range(10):
      if i > 1:
          print('0과 1만 필요해!')
          break  # i 가 1보다 커지면 종료)
      print(i)
  # 0
  # 1 
  # 0과 1만 필요해!
  ```
  
  - continue
    - continue 이후 코드는 수행하지 않고, 반복 수행
  
  ```python
  for i in range(6):
      if i % 2 == 0:
          continue # i % 2 == 0 이라면 print 로 내려가지 않고 다시 위로가서 반복문 실행
      print(i)
  # 1
  # 3
  # 5
  ```
  
  - for-else
    - 끝까지 반복문 실행 후, else 실행
      - break 을 통해 중간에 종료되는 경우 else 실행 X
  
  ```python
  for char in 'apple':
      if char == 'b':
          print('b!')
          break
  else:
      print('b가 없습니다')  # b가 없이 for문 종료 후 else 진행
  # b가 없습니다
  
  for char in 'banana':
      if char == 'b':
          print('b!')
          break            # b가 있어서, break 실행 / else문 실행 X
  else:
      print('b가 없습니다')  
  # b!
  ```
  
  - pass
    - 아무것도 하지 않음

---

## 함수 Funtion

---

![함수.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/0fd93112-f6f7-409a-ba4d-bf3b84067bb2/%ED%95%A8%EC%88%98.png)

- 특정한 기능을 하는 코드의 조각(묶음)

- 특정 코드를 매번 다시 작성 X , 필요 시 호출하여 사용

- 기본 구조
  
  - **선언 , 호출 (생성 , 사용) define & call**
    - def 키워드 사용
    - parameter(재료) 를 넘겨줄 수 있음
    - 함수는 동작 후에 return 을 통해 결과 값 전달
  
  ```python
  def function_name(parameter):
      실행 코드
      return returning_value
  
  # parameter가 없는 경우
  def foo(): # 생성
      return True
  foo() # 선언
  
  # parameter가 있는 경우
  def add(x,y): # 생성
      return x + y
  add(2,3) # 선언
  
  num1 = 0
  num2 = 1
  def func1(a,b): # 3. func1(0,5) 의 return 은 5
      return a+b
  def func2(a,b): # 3. func2(5,1) 의 return 은 4
      return a-b
  def func3(a,b):  # 2. func1(0,5) + func2(5,1) -> func1, fun2로 이동
      return func1(a,5) + func2(5,b)
  result = func3(num1,num2) # 1. func3(0,1) -> func3로 이동
  print(result) # 4. func3 = func1 + func2 -> func3 = 5 + 4
  # 9
  ```
  
  ---
  
  - **입력 input**
    
    - parameter
      
      - 함수를 정의할 때, 함수 내부에서 사용되는 변수 (선언할 때)
    
    - argument
      
      - 함수를 호출할 때, 넣어주는 값 (호출할 때)
      
      - func_name(argument) 소괄호 안에 할당
        
        - 필수 argument : 반드시! 없으면 에러
        - 선택 argument : 없으면 기본 값
      
      - positional arguments
        
        - 기본적으로 함수 호출 시 argument는 위치에 따라 함수 내에 전달
        
        ```python
        def add(x,y):
            return x + y
        
        add(2,3)
        
        x=2, y=3
        ```
      
      - keyword arguments
        
        - 직접 변수의 이름으로 특정 argument를 전달
        - keyword 다음에 positional 활용 불가
        
        ```python
        add(x = 2, y = 5)
        add(2, y = 5)
        
        add(x = 2, 5) -> ERROR 발생
        ```
      
      - default arguments values
        
        - 기본 값 지정하여, 함수 호출 시, argument 값 설정하지 않도록 함
        - 앞에서 디폴트가 있으면 뒤에도 디폴트가 있어야 함
        
        ```python
        def add(x,y=0):
            return x + y
        
        add(2)
        
        x=2, y=0
        ```
      
      - 가변 인자 (*args)
        
        - 여러 개의 positional arguments 를 하나의 필수 parameter로 받아서 사용
        - 정해지지 않은 여러 개의 arguments 처리할 때 사용
        - 주로 튜플이나 리스트를 언패킹
        
        ```python
        def add(*args): # 몇개를 positional argument로 받을지 모르기 때문
                for arg in args:
                        print(arg)
        add(2)
        add(2,3,4,5) # 4개도 받을 수 있음
        
        def func(*args):
            print(args)
            print(type(args))
        func(1,2,3,'a','b')
        # (1,2,3,'a','b')
        # <class 'tuple'>
        
        def sum_all(*numbers):
            return = 0
            for number in numbers: 
                result += number # argument 들을 계속해서 더하기
            return result
        print(sum_all(1,2,3)) # 6
        print(sum_all(1,2,3,4,5,6)) # 21
        ```
      
      - 가변 키워드 인자 (**kwargs)
        
        - 몇개의 키워드 인자를 받을지 모르는 함수를 정의할 때 유용
        - 딕셔너리로 묶여 처리, parameter 에 ** 를 붙여 표현
        
        ```python
        def family(**kwargs):
            for key, value in kwargs.items(): # items() -> 튜플 형태
                        print(key,":", value) # print(f'{key} : {value}')
        family(father='아부지',mother='어무니',baby='아기') 
        # father : 아부지
        # mother: 어무니
        # baby : 아기
        
        def print_family_name(father,mother,**pets):
                print('아버지:',father)
                print('어머니:',mother)
                if pets:
                        print('반려동물들..')
                        for species, name in pets.items():
                                print(f'{species} : {name}') # print(species,":", name)
        print_family_name('아부지','어무이',dog='멍멍이', cat='냥냥이')
        # 아버지 : 아부지
        # 어머니 : 어무이
        # 반려동물들..
        # dog : 멍멍이
        # cat : 냥냥이
        
        def my_url(**kwargs):
            url = '<https://api.go.kr>?'
            for key,value in kwargs.items():
                url += key+'='+value+'&'
            return url
        print(my_url(sidoname='서울', key='asdf'))
        # <https://api.go.kr?sidoname=서울&key=asdf&>
        ```
      
      - 가변 인자(*args) + 가변 키워드 인자(*kwargs) 동시 사용 예시
        
        ```python
        def print_family_name(*parents,**pets):
                print('아버지:',parents[0])
                print('어머니:',parent[1])
                if pets:
                        print('반려동물들..')
                        for title, name in pets.items():
                                print('{}:{}'.format(title,name))
        print_family_name('아부지','어무이',dog='멍멍이', cat='냥냥이')
        # '아부지','어무이'는 일반 값으로 들어가서 가변인자로 들어감
        # dog='멍멍이', cat='냥냥이' 는 키워드 이기 때문에 가변 키워드 인자
        
        # 아버지 : 아부지
        # 어머니 : 어무이
        # 반려동물들..
        # dog : 멍멍이
        # cat : 냥냥이
        ```
      
      - 패킹 / 언패킹
        
        - 패킹 = 여러 개의 데이터를 묶어서 변수에 할당
        - 언패킹 = 시퀀스 속 요소들을 여러 개의 변수에 나누어 할당하는 것
        - 언패킹 시, 변수와 요소의 개수가 동일해야 함.
        - 언패킹 시, 왼쪽의 변수에 `* (asterisk)` 를 붙이면, 할당하고 남은 요소를 리스트에 담을 수 있음
        
        ```python
        # 패킹 
        numbers = 1,2,3,4,5
        print(numbers) # (1,2,3,4,5)
        
        # 언패킹
        numbers = (1,2,3,4,5)
        a,b,c,d,e, = numbers
        print(a,b,c,d,e) # 1 2 3 4 5
        
        numbers = (1,2,3,4,5)
        a,b*rest = numbers # 1,2 를 제외한 나머지를 rest에 대입
        print(a,b,rest) # 1 2 [3,4,5]
        a,*rest,e = numbers # 1,5 를 제외한 나머지를 rest에 대입
        print(rest) # [2,3,4]
        ```

  ---

- **문서화 docstring**

  ---

- **범위 scope**
  
  - 함수는 코드 내부에 local scope를 생성, 그 외 공간인 global scope로 구분
  
  - **scope**
    
    - global scope
      - 코드 어디서나 참조할 수 있는 공간
    - local scope
      - 함수가 만든 scope / 함수 내부에서만 참조 가능
  
  - **variable**
    
    - global variable
      - global scope에 정의된 변수
    - local variable
      - local scope에 정의된 변수
  
  - **변수의 수명 주기 lifecycle**
    
    - built-in scope
      - 파이썬이 실행된 이후부터 영원히 유지
    - global scope
      - 모듈이 호출된 시점 이후 / 인터프리터가 끝날 때까지 유지
    - local scope
      - 함수가 호출될 때 생성 / 함수가 종료될 때까지 유지
    
    ```python
    def func():
            a = 20
            print('local', a) # local 20
    func()
    print('gloabl', a) # Error -> 'a' is not defined
    
    # a 는 함수 안에 Local scope에만 존재
    ```
  
  - **이름 검색 규칙 Name Resolution**
    
    - 파이썬에서 사용되는 이름은 이름 공간에 저장되어 있음
    
    - 아래 순서대로 이름을 찾아나감
    
    - **LEGB Rule**
      
      - Local scope 지역 범위
      - Enclosed scope 지역 범위 한 단계 위
      - Global scope 최상단에 위치
      - Built-in scope 모든 것을 담고 있는 범위
      
      `함수 내에서는 바깥 scope의 변수에 접근은 가능하나 수정은 불가`
      
      ```python
      print(sum) # <built-in fuction sum>
      print(sum(range(2))) # 1
      sum = 5
      print(sum) # 5
      print(sum(range(2))) # Error -> 'int' object is not callable
      
      # Global scope 이름 공간의 sum 변수에 값 5가 할당
      # 이후 global scope 에서 sum 은 LEGB에 의해 5가 먼저 탐색
      
      a = 0
      b = 1
      def enclosed():
              a = 10
              c = 3
              def local(c):
                      print(a,b,c) # 10 1 300 -> a,b 밖에서 찾기(가까운 a) 
              local(300) # local(300)이 local(c)로 가기 때문에 c = 300 
              print(a,b,c) # 10 1 3 -> a,c는 local에 10,3 / b는 밖에서 찾기 
      enclosed()
      print(a,b) # 0 1 -> a,b는 local에 0,1
      ```
    
    - global
      
      - 현재 코드 블록 전체에 적용
      - 나열된 식별자(이름)이 global variable임을 나타냄
      - global에 나열된 이름은 같은 코드 블록에서 global 앞에 등장 X
      - global에 나열된 이름은 parameter, for루프 대상, 클래스/함수 정의 등 정의 X
    
    ```python
    a = 10
    def func1():
            global a
            a = 3
    print(a) # 10
    func1() # func1()이 실행 됨
    print(a) # 3 -> 위에서 함수가 실행 되었기 때문에 global a -> a = 3 으로 변경
    
    ### 주의 사항
    a = 10
    def func1():
            print(a) # global a 선언 전에 사용        
            global a
            a = 3
    print(3) 
    func1() 
    print(a)
    # Error -> 'a' is used prior to global declaration
    
    ### 주의 사항
    a = 10
    def func1(a):        
            global a # parameter에 global 사용 불가
            a = 3
    print(a) 
    func1(3) 
    print(a)
    # Error -> 'a' is parameter and global
    ```
    
    - nonlocal
      - global을 제외하고 가장 가까운(둘러싸고 있는) scope의 변수를 연결
      - **이미 존재하는 이름과의 연결만 가능**
      - nonlocal에 나열된 이름은 같은 코드 블록에서 nonlocal 앞에 등장 X
      - nonlocal에 나열된 이름은 parameter, for루프 대상, 클래스/함수 정의 등 정의 X
    
    ```python
    x = 0
    def func1():
            x = 1
            def func2():
                    nonlocal x
                    x = 2
            func2()
            print(x) # 2 
    func1()
    print(x) # 0
    ```

  ---

- **결과값 output**
  
  - 값에 따른 함수의 종류
    - Void function
      - 명시적 return 값이 없는 경우, None을 반환하고 종료
    - value returning function
      - 함수 실행 후, return문을 통해 값 반환
      - return을 하게 되면, 값 반환 후 함수 종료
    - `print 와 return의 차이점`
      - print는 호출될 때마다 값 출력 (주로 테스트를 위해 사용)
      - 데이터 처리를 위해서는 return 사용
  
  ```python
  # void function 예시
  def void_product(x,y):
        print(f'{x} x {y} = {x*y}')
  void_product(4,5) # 4 x 5 = 20 -> 호출될 때마다 값 출력
  ans = void_product(4,5) # 4 x 5 = 20
  print(ans) # None -> ans에 값을 반환하지는 않음
  
  # value returning function 예시
  def value_returning_product(x,y):
        return x * y
  value_returning_product(4,5)
  ans = value_returning_product(4,5)
  print(ans) # 20 
  
  #return은 항상 하나만 반환 하기 때문에...
  def munus_and_product(x,y):
    return x-y , x*y # 반환 값으로 튜플 사용
  y = minus_and_product(4,5)
  print(y) # (-1,20) # 반환 값으로 튜플 사용
  print(type(y)) # <class 'tuple'>
  ```

  ---

- **분해** `Decomposition`
  
  - 기능을 분해하고 재사용 가능하게 만들고 !

- **추상화** `Abstraction`
  
  - 복잡한 내용을 모르더라도 사용할 수 있도록
  - 재사용성, 가독성, 생산성
  
  ---

- 내장 함수 Built-in function
  
  ![빌트인함수.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/baaf26bd-704d-4258-acab-e9a5a8e47466/%EB%B9%8C%ED%8A%B8%EC%9D%B8%ED%95%A8%EC%88%98.png)
  
  - 파이썬 기본 함수 `dir(__builtins__)`
  
  - map `map(function, iterable)`
    
    - 순회 가능한 데이터 구조(iterable)의 모든 요소에 함수 적용, 결과를 map object로 변환
    
    ```python
    numbers = [1,2,3]
    result = map(str, numbers)
    print(result, type(result))
    # <map object at 0x00000208CBE36E20> <class 'map'>
    print(list(result))
    # ['1','2','3']
    
    n,m = map(int, input().split()) # input : 3 5
    print(n,m) # 3 5
    print(type(n),type(m))
    # <class 'int'> <class 'int'>
    ```
  
  - filter `filter(function, iterable)`
    
    - 순회 가능한 데이터 구조(iterable)의 모든 요소에 함수 적용,
      
      결과가 True인 것들을 filter object로 반환

    ```python
    def odd(n):
            return n % 2
    numbers = [1,2,3]
    result = filter(odd,numbers)
    print(result,type(result))
    #<filter object at 0x00000143BEAD4E80> <class 'filter'>
    print(list(result))
    # [1,3]
    ```

- zip `zip(*iterables)`
  
  - 복수의 데이터 구조(iterable)를 모아 튜플을 원소로 하는 zip object를 반환
  
  ```python
  girls = ['jane','ashley']
  boys = ['justin','eric']
  pair = zip(girls, boys)
  print(pair, type(pair))
  # <zip object at 0x000001BE34E6F880> <class 'zip'>
  print(list(pair))
  # [('jane', 'justin'), ('ashley', 'eric')]
  ```

- abs()
  
  - 숫자형 자료(int, float)가 들어오면 절댓값 반환
  - 복소수형 자료(complex)가 들어오면 해당하는 자료의 크기 반환
  
  ```python
  def my_abs(x):
      if type(x) == complex: # 복소수 타입일 경우
          return (x.imag**2 + x.real**2) ** (1/2)
      else:
          if x == 0:
              return x ** 2
          if x < 0:
              return x * -1
          else:
              return x
  print(my_abs(3+4j)) # 5.0
  print(my_abs(-5)) # 5
  print(abs(3+4j), abs(-5)) # 5.0 5
  ```

- all()
  
  - 인자로 받는 모든 요소가 참이거나, 비어있으면 True
  
  ```python
  def my_all(elements):
      for element in elements:
          if not element: # 하나라도 거짓이면
              return False
      return True # 비어있는 경우 반복문을 돌지 않고 바로 return 값으로 옴
  print(my_all([])) # True
  print(my_all([1, 2, 5, '6'])) # True
  print(my_all([[], 2, 5, '6'])) # False
  print(all([]), all([1, 2, 5, '6']), all([[], 2, 5, '6'])) 
  # True True False
  ```

- any()
  
  - 인자로 받는 요소 중 하나라도 참이면 True , 비어있으면 False
  
  ```python
  def my_any(elements):
          for element in elements:
                  if element:
                          return True
          return False
  print(my_any([1, 2, 5, '6'])) # True
  print(my_any([[], 2, 5, '6'])) # True
  print(my_any([0])) # False
  print(any([1, 2, 5, '6']), any([[], 2, 5, '6']), any([0]))
  # True True False
  ```

- 외장 함수
  
  - import 문을 통해 사용
  - 외부 라이브러리에서 제공하는 함수

- 사용자 정의 함수
  
  - 사용자가 직접 만드는 함수
  
  ---

- 예제 ) 자릿수 더하기
  
  ```python
  def sum_of_digit(num):
          sum = 0
          while num > 0:
                  d,m = divmod(num, 10)
                  num = d
                  sum += m
          return sum
  print(sum_of_digit(1234)) # 10
  print(sum_of_digit(4321)) # 10
  
  # 재
  def sum_of_digit(num):
          if num < 10:
                  return num
          else:
                  num, remainder = divmod(num, 10)
                  return sum_of_digit(num) + remainder
  print(sum_of_digit(1234)) # 10
  print(sum_of_digit(4321)) # 10
  ```

- 예제 ) 회문 / 팰린드롬
  
  ```python
  def is_pal(word):
      if word == word[::-1]:
          return True
      else:
          return False
  print(is_pal('tomato')) # False
  print(is_pal('racecar')) # True
  print(is_pal('azza')) # True
  
  # while 사용
  def is_pal_while(word):
          while len(word) > 1:
                  if word[0] == word[-1]:
                          word = word[1:-1]
                  else:
                          return False
          return True
  
  # 재귀
  def is_pal_recursive(word):
          if len(word) <= 1:
                  return True
          elif word[0] == word[-1]:
                  return is_pal_recursive(word[1:-1])
          else:
                  return False
  ```

- 예제 ) 연속된 숫자는 제거
  
  ```python
  numbers = [8, 8, 1, 1, 0, 1, 1]
  result = []
  for idx, num in enumerate(numbers): # idx 0 , num 8 / idx 1 , num 8 ........
      if idx == 0 or result[-1] != num: #idx 0 이거나, result의 마지막 인자 != num 이면!
          result.append(num)
  print(result)
  ```

---

- **lambda 함수**
  
  - 익명 함수
  - return문을 가질 수 없음
  - 간편 조건문 외 조건문이나 반복문을 가질 수 없음
  - 간결하고 def 사용 불가능한 곳에서 사용 가능
  
  ```python
  lambda [parameter] : 표현식
  
  def triangle_area(b,h):
          return 0.5 * b * h
  print(triangle_area(5,6))
  # 15.0
  
  triangle_area = lambda b, h : 0.5 * b * h
  print(triangle_area(5,6))
  # 15.0
  ```
  
  ---

- **재귀 함수 recursive function**
  
  - 자기 자신을 호출하는 함수
  - 1개 이상의 종료 상황(base case)이 존재, 수렴하도록 작성
  - base case에 도달할 때까지 함수 호출
  - 메모리 스택이 넘치면 프로그램이 동작하지 않음
  - 파이썬에서 최대 재귀 깊이가 1,000번으로 이를 넘어가면 recursion Error
  
  ```python
  # 팩토리얼
  def factorial(n):
          if n == 0 or n == 1:
                  return 1
          else:
                  return n * factorial(n-1) # 4* f3 -> 4*3 *f2 -> 4*3*2 *f1 -> 4*3*2*1
  print(factorial(4)) # 24
  
  # 위 재귀 함수를 반복문으로 표현 가능
  # 재귀 호출은 변수사용을 줄여주지만, 입력값이 커질 수록 연산 속도가 오래 걸림
  def fact(n):
          result = 1
          while n > 1: # n 이 1보다 큰 동안
                  result *= n # result 에 n을 계속 곱하기
                  n -= 1 # n 은 1씩 작아짐
          return result
  print(fact(4)) # 24
  ```

---

- 모듈 module
  - 다양한 기능을 하나의 파일로
- 패키지 package
  - 다양한 파일을 하나의 폴더로
- 라이브러리 library
  - 다양한 패키지를 하나의 묶음으로
- pip
  - 이것을 관리하는 관리자
- 가상환경
  - 패키지의 활용 공간

---

## 모듈과 패키지

---

- 모듈
  - 특정 기능을 하는 코드를 파이썬 파일(.py) 단위로 작성 한 것
- 패키지
  - 특정 기능과 관련된 여러 모듈의 집합
  - 패키지 안에는 또 다른 서브 패키지를 포함

```python
# 모듈과 패키지 불러오기
# 외부 개발자들이 만들어 놓은 코드들을 가져다 쓰기

import module
from module import var,function,class
from module import *  # 모듈 내 모든 것

from package import module 
from package.module import var,function,class
```

---

## 표준 라이브러리

---

- [](https://docs.python.org/ko/3/library/index.html)[파이썬 표준 라이브러리 &#8212; Python 3.10.5 문서](https://docs.python.org/ko/3/library/index.html)

- **파이썬 패키지 관리자 pip**
  
  - 패키지 설치 (최신 버전, 특정 버전, 최소 버전 명시하여 설치 가능
  
  - 이미 설치 되었다면, 알림 + 설치 X
    
    ```python
    $ pip install SomePackage
    $ pip install SomePackage==1.0.5
    $ pip install ‘SomePackage≥1.0.4’
    삭제 → $ pip uninstall SomePackage
    목록 → $ pip list
    정보 → $ pip show SomePackage
    
    패키지 관리 (패키지 기록 파일 이름은 requirements.txt)
    $ pip freeze > requirements.txt
    $ pip install -r requirements.txt 
    ```

---

## 사용자 모듈과 패키지

---

- 패키지는 여러 모듈 / 하위 패키지로 구조화
  - 활용 예시 : package.module
- 모든 폴더에는 `__init__.py` 를 만들어 패키지로 인식 (3.3부터는 없어도 되지만, 하위 버전 호환)

---

## 가상환경

---

- 파이썬 표준 라이브러리가 아닌 외부 패키지와 모듈을 사용하는 경우
  
  모두 pip를 통해 설치 해야함

- 복수의 프로젝트를 하는 경우 버전이 상이할 수 있음.
  
  - 과거 외주 프로젝트 - django 2.x
  - 신규 회사 프로젝트 - django 3.x

- 가상환경을 통해 프로젝트 별 독립적 패키지 관리 가능

- 특정 디렉토리에 가상 환경을 만들고, 고유한 파이썬 패키지 집합을 가질 수 있음

- 생성
  
  - $ python -m venv <폴더명>
    
    - 해당 디렉토리에 별도의 파이썬 패키지가 설치 됨
      
      ![가상환경 활성화.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/d1f7d194-5423-4a55-b86f-3d509343b69f/%EA%B0%80%EC%83%81%ED%99%98%EA%B2%BD_%ED%99%9C%EC%84%B1%ED%99%94.png)
    
    - 가상 환경 비활성화는 $ deactivate 명령어 사용
