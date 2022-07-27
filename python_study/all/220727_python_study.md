## 객체 지향 프로그래밍 OOP

---

![객체지향.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/08379e8f-63e8-4cd0-a8f3-67ed5c58e429/%EA%B0%9D%EC%B2%B4%EC%A7%80%ED%96%A5.png)

- 프로그램을 여러 개의 독립된 객체들과 그 객체 간의 상호작용으로 파악하는 프로그래밍 방법
- 변수 + 함수 (정보 + 행동)
- 데이터와 기능(메서드) 분리 / 추상화된 구조(인터페이스)
- 현실 세계를 프로그램 설계에 반영 (**추상화**)
- 장점과 단점
  - 클래스 단위 모듈화 → 대규모 소프트웨어 개발 적합
  - 필요 부분만 수정 가능 → 유지 보수가 쉬움
  - 다양한 객체들의 상호 작용 구조 만들어야 함 → 설계 시 많은 시간 필요
  - 실행 속도가 상대적으로 느림 → 절차 지향 프로그래밍과 컴퓨터 처리 구조 비슷

---

## OOP 기초

---

![객체.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8fc8f13d-60ef-417d-b9f6-fe12b3060a97/%EA%B0%9D%EC%B2%B4.png)

- 객체(컴퓨터 과학)
  - `속성 Attribute` + `기능 Method`
  - `속성`과 `행동`으로 구성된 모든 것
  - `변수` 와 `메서드`
- 파이썬은 모든 것이 객체 (object)
  - 속성과 행동이 존재!

```python
[3,2,1].sort() -> 리스트.정렬() / 객체.행동()
'banana'.upper()-> 문자열.대문자로() / 객체.행동() / 'banana'는 문자열 타입의 인스턴스

[1,2,3] , [1] , [], ['hi'] -> 모두 리스트 타입(클래스)의 객체
'' , 'hi' , '파이썬' -> 모두 문자열 타입(클래스)의 객체
```

- 객체 object 는 특정 타입의 인스턴스 instance 이다.
  
  - 123, 900 5 는 모두 int 의 인스턴스
  - ‘hello’, ‘bye’ 는 모두 str 의 인스턴스
  - [232,89,1], []은 모두 list 의 인스턴스

- 인스턴스
  
  - 클래스로 만든 객체 → `인스턴스`
  - 특정 타입의 객체
  - 클래스를 만든다 == 타입을 만든다

- 객체의 특징
  
  - 타입 type
    - 어떤 연산자 (operator) 와 조작 (method) 이 가능한가?
  - 속성 attribue
    - 어떤 상태 (데이터) 를 가지는가?
  - 조작법 method
    - 어떤 행위 (함수) 를 할 수 있는가?

---

- 객체와 클래스 기본 문법
  
  ```python
  - 클래스 정의 (앞글자 대문자!)
  class My Class:
  
  - 인스턴스 생성
  my_instance = MyClass()
  
  -메서드 호출 
  my_instance.my_method()
  
  -속성
  my_instance.my_attribute
  ```

- 클래스와 인스턴스
  
  - 객체의 설계도 (클래스)를 가지고, 객체 (인스턴스)를 생성
  - 클래스
    - 객체들의 분류 / 설계도 class
  - 인스턴스
    - 하나하나의 실체 / 사례 instance

---

객체 비교하기

- `==`
  - 동등한 equal
  - 변수가 참조하는 객체가 동등한 경우 True (내용 같지만 주소는 다름)
  - 동일 대상을 확인은 NO
  - Ex) 쌍둥이 ? 똑같이 보이지만 둘은 다른 사람
- `is`
  - 동일한 identical
  - 두 변수가 동일한 객체를 가리키는 경우 True (주소까지 같음)

```python
a = [1,2,3]
b = [1,2,3] # 생긴것은 같지만 주소는 다름
print(a==b, a is b) # True False

a = [1,2,3]
b = a  # 주소 같음
print(a==b, a is b) # True True
```

---

- OOP 속성 (데이터,정보,상태) → 변수
  
  - 특정 데이터 타입 / 클래스의 객체들이 가지게 될 상태 / 데이터
  - 클래스 변수 / 인스턴스 변수
  
  ```python
  class Person:
          blood_color = 'red'  # 클래스 변수
          population = 100   # 클래스 변수
  
          def __init__(self, name):
                  self.name = name  # 인스턴스 변수
  
  person1 = Person('지민')
  print(person1.name)  # 지민 
  ```

- 인스턴스 변수
  
  - 개인적으로 가지고 있는 속성
  - 각 인스턴스들의 고유한 변수
  - 생성자 메서드 `__init__` 에서 self.<name>으로 정의
  - 인스턴스가 생성된 이후 <instance>.<name>으로 접근 및 할당
  
  ```python
  class Person:
          def __init__(self, name):  # 인스턴스 변수 정의
                  self.name = name
  
  john = Person('john')    # 인스턴스 변수 접근 및 할당
  print(john.name)  # john
  john.name = 'John Kim'    # 인스턴스 변수 접근 및 할당
  print(john.name)  # John Kim
  ```

- 클래스 변수
  
  - 클래스 선언 내부에서 정의
  - <classname>.<name>으로 접근 및 할당
  - 인스턴스로 클래스 변수 조회 가능 (공통 사용 가능)
    - <instance>.<클래스 변수>
  
  ```python
  class Circle():
          pi = 3.14  # 클래스 변수 정의
          def __init__(self, r):
                  self.r = r  # 인스턴스 변수
  
  c1 = Circle(5)  # 인스턴스 변수 접근 및 할당
  c2 = Circle(10)
  
  print(Circle.pi)  # 3.14  -> 클래스 내부에 값 존재
  print(c1.pi)  # 3.14  -> 인스턴스 내부에 값이 없음 -> 해당 클래스에서 찾기
  print(c2.pi)  # 3.14
  
  Circle.pi = 5  # 클래스 변수 변경
  print(Circle.pi)  # 5 
  print(c1.pi)  # 5  -> 인스턴스 내부에 값이 없음 -> 해당 클래스에서 찾기
  print(c2.pi)  # 5
  ```
  
  - 사용자가 몇 명인지 확인하고 싶다?
  - 인스턴스가 생성 될 때마다 클래스 변수가 늘어나도록 설정
  
  ```python
  class Person:
      count = 0  # 클래스 변수 
  
      def __init__(self, name):  # 생성자 메서드 (인스턴스 메서드)
          self.name = name   # 인스턴스 변수 설정
          Person.count += 1   # 클래스 Person . 변수 count 에 +1 을 해줘라
  
  person1 = Person('아이유')   # Person 클래스의 인스턴스 생성
  person2 = Person('이찬혁')
  
  print(Person.count)  # 2
  ```

- 클래스 변수 / 인스턴스 변수
  
  - 클래스 변수 변경 시 항상! `클래스.클래스변수` 형식으로 변경
  - 인스턴스 변수가 없다면 해당 클래스 변수를 가져 옴
  - 클래스 변수 변경 시, 인스턴스 변수가 없는 애들은 같이 변경 됨
  - 인스턴스 변수를 변경? → 클래스 변수는 변동 X / `인스턴스.변수` 로 변경
  
  ```python
  class Circle():
      pi = 3.14    # 클래스 변수 정의
  
      def __init__(self, r):
          self.r = r    # 인스턴스 변수
  
  c1 = Circle(5)    # 인스턴스 생성
  c2 = Circle(10)
  
  print(Circle.pi)  # 3.14
  print(c1.pi)  # 3.14   -> 인스턴스에 값이 없으니, 해당 클래스에서 찾기
  print(c2.pi)  # 3.14   -> 인스턴스에 값이 없으니, 해당 클래스에서 찾기
  
  Circle.pi = 5  # 클래스 변수 변경
  print(Circle.pi)  # 5
  print(c1.pi)  # 5   -> 인스턴스에 값이 없으니, 해당 클래스에서 찾기
  print(c2.pi)  # 5   -> 인스턴스에 값이 없으니, 해당 클래스에서 찾기
  
  c2.pi = 4  # 인스턴스 변수 변경
  print(Circle.pi)  # 5 (클래스변수)
  print(c1.pi)  # 5 (클래스 변수)
  print(c2.pi)  # 4  -> 새로운 인스턴스 변수 생성!
  ```

---

- OOP 메서드
  
  - 클래스 안에 있는 함수
    - **인스턴스** 메서드 / **클래스** 메서드 / **정적** 메서드
  - 특정 데이터 타입 / 클래스의 객체에 공통적으로 적용 가능한 행위(함수)
  
  ```python
  class Person:
  
          def talk(self):
                  print('안녕')
          def eat(self,food):
                  print(f'{food}를 냠냠')
  
  person1 = Person()
  person1.talk()  # 안녕
  person1.eat('피자')  # 피자를 냠냠
  person1.eat('치킨')  # 치킨를 냠냠
  ```

---

### 인스턴스 메서드

- 인스턴스 변수를 사용하거나, 인스턴스 변수에 값을 설정
- 클래스 내부에 정의되는 메서드의 기본
- 인스턴스 메서드는 클래스 변수, 인스턴스 변수 둘 다 사용 가능!
- 호출 시, 첫 인자로 인스턴스 자기자신 `self` 전달!

```python
class MyClass:
        def instance_method(self, arg1, ...):

my_instance = MyClass()
my_intance.instance_method(...)
```

- 생성자 constructor 메서드
  
  - 인스턴스 객체가 생성될 때 자동으로 호출되는 메서드
  - 인스턴스 변수들의 초기 값을 설정
    - 인스턴스 생성
    - `__init__` 메서드 자동 호출
  
  ```python
  class Person:
          def __init__(self, name):
                  print(f'인스턴스가 생성되었습니다. {name}')
  
  person1 = Person('지민')  # 인스턴스가 생성되었습니다. 지민
  ```

- 소멸자 destructor 메서드
  
  - 인스턴스 객체가 소멸되기 직전에 호출되는 메서드
  
  ```python
  class Person:
          def __del__(self):
                  print('인스턴스가 사라졌습니다.')
  
  person1 = Person()
  del person1  # 인스턴스가 생성되었습니다.
  ```

- 매직 메서드 (스페셜 메서드)
  
  - Double underscore `__` 가 있는 메서드
  - 특수한 동작을 위해 만들어짐
  - 특정 상황에 자동으로 불림
  - 객체의 특수 조작 행위를 지정 (함수, 연산자 등)
  
  ![매직메서드.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/d75878cc-3faa-44e6-b967-61566be51104/%EB%A7%A4%EC%A7%81%EB%A9%94%EC%84%9C%EB%93%9C.png)
  
  ```python
  __str__ : 해당 객체의 출력 형태를 지정
  - 프린트 함수 호출 시, 자동 호출
  - 어떤 인스턴스를 출력하면 __str__의 return 값이 출력
  __gt__ : 부등호 연산자 ( > , greater than )
  ```
  
  ```python
  class Circle:  # 클래스 생성
  
      def __init__(self, r):  # 생성자 메서드
          self.r = r  # 인스턴스 변수 설정
  
      def area(self):
          return 3.14 * self.r * self.r
  
      def __str__(self):   # print()함수 사용시 호출
          return f'[원] radius: {self.r}' 
  
      def __gt__(self, other):   # 크기 비교 / True , False
          return self.r > other.r
  
  c1 = Circle(10)
  c2 = Circle(1)
  
  print(c1)  # [원] radius: 10
  print(c2)  # [원] radius: 1
  print(c1 > c2)  # True
  print(c1 < c2)  # False
  ```

---

### 클래스 메서드

- 클래스가 사용할 메서드

- 클래스는 인스턴스 변수 사용 불가능!

- `@classmethod` 데코레이터를 사용하여 정의

- 호출 시, 첫 인자로 클래스 `cls` 가 전달
  
  ```python
  class Myclass:
  
          @classmethod
          def class_method(cls, arg1, ...):
  
  Myclass.class_method(...)
  ```
  
  ```python
  class Person:
      count = 0
      def __init__(self, name):
          self.name = name
          Person.count += 1
  
      @classmethod
      def number_od_population(cls):
          print(f'인구수는 {cls.count}입니다.')
  
  person1 = Person('아이유')
  person2 = Person('이찬혁')
  print(Person.count)
  ```

- 데코레이터
  
  - 함수를 어떤 함수로 꾸며서 새로운 기능 부여
  - @데코레이터(함수명) 형태로 함수 위에 작성
  - 순서대로 적용 → 작성 순서 중요!!
  
  ```python
  데코레이터 안쓰면?
  
  def hello():
      print('hello')
  
  # 데코레이팅 함수
  def add_print(original):  # 파라미터로 함수 받음
      def wrapper():    # 함수 내에 새로운 함수 선언
          print('함수 시작')  # original 함수 꾸미기
          original()
          print('함수 끝')   # original 함수 꾸미기
      return wrapper
  
  add_print(hello)()
  # 
  함수 시작
  hello
  함수 끝
  
  print_hello = add_print(hello)
  print_hello()
  # 
  함수 시작
  hello
  함수 끝
  ```
  
  ```python
  데코레이터 사용!
  
  # 데코레이팅 함수
  def add_print(original):
      def wrapper():
          print('함수 시작')
          original()
          print('함수 끝')
      return wrapper
  
  @add_print  # add_print를 사용해서 print_hello()함수를 꾸며주도록 하는 명령어
  def print_hello():
      print('hello')
  
  print_hello()
  # 
  함수 시작
  hello
  함수 끝
  ```

- 인스턴스와 클래스 간의 이름 공간 namespace
  
  - 클래스를 정의하면, 클래스와 해당하는 이름 공간 생성
  - 인스턴스 생성 시, 인스턴스와 이름 공간 생성
  - 인스턴스에서 특정 속성에 접근하면, 인스턴스 - 클래스 순으로 탐색
  
  ```python
  class Person:
      name = 'unknown'
  
      def talk(self):
          print(self.name)
  
  p1 = Person()
  p1.talk()  # unknown -> 클래스 변수 출력
  
  p2 = Person()
  p2.talk()  # unknown -> 클래스 변수 출력
  p2.name = 'kim' # 인스턴스 변수 정의
  p2.talk()  # kim  -> 인스턴스 변수 출력
  
  print(Person.name) # unknown
  print(p1.name) # unknown
  print(p2.name) # kim
  ```

---

### 정적 메서드 / 스태틱 메서드

- 인스턴스, 클래스 변수 둘 다 사용하지 않는 경우 사용
  - 객체 상태나 클래스 상태 수정 불가!
- 속성을 다루지 않고, 기능만 하는 메서드를 정의 할 때 사용
- @staticmethod 데코레이터를 사용하여 정의
- 일반 함수처럼 동작
- 클래스의 이름 공간에 귀속 → 해당 클래스로 한정하는 용도로 사용

```python
class MyClass:

        @staticmethod
        def static_method(arg1, ...):

MyClass.static_method(...)
```

```python
class Person:
    count = 0  # 클래스 변수 생성
    def __init__(self, name):  
        self.name = name
        Person.count += 1

    @staticmethod
    def check_rich(money):  # 스태틱 메서드 / self , cls 사용 X
        return money > 10000

person1 = Person('아이유')
person2 = Person('이찬혁')
print(Person.check_rich(100000)) # True  -> 스태틱메서드 클래스로 접근 가능
print(person1.check_rich(100000))  # True  -> 스태틱메서드 클래스로 접근 가능
```

---

### 메서드 3가지 예시

---

```python
class MyClass:

    def method(self):
        return 'instance method', self

    @classmethod
    def classmethod(cls):
        return 'class method', cls

    @staticmethod
    def staticmethod():
        return 'static method'

obj = MyClass()

**** 인스턴스 메서드 호출 결과**
print(obj.method())
# ('instance method', <__main__.MyClass object at 0x000002ADEF474DC0>)
print(MyClass.method(obj))
# ('instance method', <__main__.MyClass object at 0x000002ADEF474DC0>)

**** 클래스 자체에서 각 메서드 호출 경우** 
print(MyClass.classmethod())
# ('class method', <class '__main__.MyClass'>)
print(MyClass.staticmethod())
# static method
MyClass.method() # 클래스에서 인스턴스 메서드 호출 불가
# TypeError: method() missing 1 required positional argument: 'self'

**** 인스턴스는 클래스와 스태틱 모두 접근 가능**
print(obj.classmethod())
# ('class method', <class '__main__.MyClass'>)
print(MyClass.classmethod())
# ('class method', <class '__main__.MyClass'>)
print(obj.staticmethod())
# static method
```

---

## 객체 지향 핵심 개념

---

- 추상화 / 상속 / 다형성 / 캡슐화

---

### 추상화

---

- 현실 세계를 프로그램 설계에 반영
  - 복잡한 것 숨기고, 필요한 것 들어내기

---

### 상속

---

- 두 클래스 사이에 부모-자식 관계를 정립하는 것 (상위-하위)

- 하위 클래스는 상위 클래스에 정의된 속성, 행동, 관계 및 제약 조건을 모두 상속 받음

- 코드의 재사용성 높아짐

- 메서드 오버라이딩 을 통해 자식 클래스에서 재정의 가능

- 상속 관계에서 이름 공간은 인스턴스- 자식 - 부모 순서

- 클래스는 상속 가능
  
  - 모든 파이썬 클래스는 object를 상속 받음
  
  ```python
  class ChildClass(ParentClass):
          pass
  ```

- 예시 - 상속이 없다면..?
  
  - 학생 / 교수 정보 나타내기 어려움
  
  ```python
  class Person:
  
      def __init__(self, name, age):
          self.name = name
          self.age = age
  
      def talk(self):
          print(f'반갑습니다. {self.name}입니다.')
  
  s1 = Person('김학생', 23)
  s1.talk()  # 반갑습니다. 김학생입니다.
  
  p1 = Person('박교수', 49)
  p1.talk()  # 반갑습니다. 박교수입니다.
  
  s1.gpa = 4.5
  p1.department = '컴퓨터 공학과'
  ```
  
  - 메서드 중복 정의
  
  ```python
  class Professor:
  
      def __init__(self, name, age, department):
          self.name = name
          self.age = age
          self.department = department
  
      ***def talk(self):
          print(f'반갑습니다. {self.name}입니다.')***
  
  class Student:
  
      def __init__(self, name, age, gpa):
          self.name = name
          self.age = age
          self.gpa = gpa
  
      ***def talk(self):
          print(f'반갑습니다. {self.name}입니다.')***
  
  p1 = Professor('박교수', 49, '컴퓨터 공학과')
  
  s1 = Student('김학생', 23, 3.5)
  ```
  
  - **상속으로 메서드 재사용 !**
  
  ```python
  class Person:
      def __init__(self, name, age):
          self.name = name
          self.age = age
  
      def talk(self):
          print(f'반갑습니다. {self.name}입니다.')
  
  class Professor(Person):
      def __init__(self, name, age, department):
          self.name = name
          self.age = age
          self.department = department
  
  class Student(Person):
      def __init__(self, name, age, gpa):
          self.name = name
          self.age = age
          self.gpa = gpa
  
  p1 = Professor('박교수', 49, '컴퓨터 공학과')
  s1 = Student('김학생', 23, 3.5)
  
  p1.talk() # 반갑습니다. 박교수입니다.
  s1.talk() # 반갑습니다. 김학생입니다.
  ```

- 상속 관련 함수와 메서드
  
  - isinstance(object, classinfo)
    - classinfo 의 instance 이거나 subclass 인 경우 True
  
  ```python
  class Person:
      pass
  
  class Professor:
      pass
  
  class Student:
      pass
  
  p1 = Professor()
  s1 = Student()
  
  print(isinstance(p1, Person)) # False
  print(isinstance(p1, Professor)) # True
  print(isinstance(p1, Student)) # False
  print(isinstance(s1, Person)) # False
  print(isinstance(s1, Professor)) # Flase
  print(isinstance(s1, Student)) # True
  
  -------------------------------------------------------------------
  
  class Person:
      pass
  
  class Professor(Person):
      pass
  
  class Student(Person):
      pass
  
  p1 = Professor()
  s1 = Student()
  
  print(isinstance(p1, Person)) # True
  print(isinstance(p1, Professor)) # True
  print(isinstance(p1, Student)) # False
  print(isinstance(s1, Person)) # True
  print(isinstance(s1, Professor)) # Flase
  print(isinstance(s1, Student)) # True
  ```
  
  - issubclass(class, classinfo)
    - class 가 classinfo의 subclass면 True
    - classinfo 는 클래스 객체의 튜플일 수 있으며, classinfo의 모든 항목 검사
  
  ```python
  class Person:
      pass
  
  class Professor(Person):
      pass
  
  class Student(Person):
      pass
  
  p1 = Professor()
  s1 = Student()
  
  print(issubclass(bool, int)) # True
  print(issubclass(float, int)) # False
  print(issubclass(Professor, Person)) # True
  print(issubclass(Professor, (Person,Student))) 
  # True -> Student 의 서브클래스는 아니다. 둘 중 하나만 True 여도 True 반환
  ```
  
  - super()
    - 자식 클래스 에서 부모 클래스 사용하고 싶은 경우
  
  ```python
  class Person:
      def __init__(self, name, age, number, email):
          self.name = name
          self.age = age
          self.number = number
          self.email = email
  
  class Student(Person):
      def __init__(self, name, age, number, email, student_id):
          self.name = name
          self.age = age
          self.number = number
          self.email = email
          self.student_id = student_id
  
  ------------------------------------------------------------------------
  
  class Person:
      def __init__(self, name, age, number, email):
          self.name = name
          self.age = age
          self.number = number
          self.email = email
  
  class Student(Person):
      def __init__(self, name, age, number, email, student_id):
          super().__init__(name, age, number, email)
          self.student_id = student_id
  ```

---

### 다중 상속

---

- 두 개 이상의 클래스를 상속

- 상속받은 모든 클래스 요소 활용 가능

- **중복 속성, 메서드**는 **상속 순서**에 의해 결정
  
  ```python
  class Person:
      def __init__(self, name):
          self.name = name
  
      def greeting(self):
          return f'얀녕, {self.name}'
  
  class Mom(Person):
      gene = 'XX'
  
      def swim(self):
          return '엄마가 수영'
  
  class Dad(Person):
      gene = 'XY'
  
      def walk(self):
          return '아빠가 걷기'
  
  class FirstChild(Dad,Mom):  # 순서대로 영향을 받는다
      def swim(self):
          return '첫째가 수영'
  
      def cry(self):
          return '첫째가 응애'
  
  baby1 = FirstChild('아가')
  
  print(baby1.cry())  # 첫째가 응애 
  print(baby1.swim())  # 첫째가 수영 -> 오버라이딩 / 덮어 쓰기
  print(baby1.walk())  # 아빠가 걷기 -> 부모 요소 상속
  print(baby1.gene)  # XY -> Dad 가 앞에 적혀있으면, Dad 정보를 받음
  ```

- mro메서드 Method Resolution Order
  
  - 해당 인스턴스의 클래스가 어떤 부모의 클래스를 가지는지 확인하는 메서드
  
  - 기존 인스턴스 → 클래스 순으로 이름 공간 탐색 과정에 상속 관계가 있다면
    
    인스턴스 → 자식 → 부모 순으로 확장

```python
print(FirstChild.mro()) 형식으로 사용
```

---

### 다형성 Polymorphism

---

- 동일한 메서드가 클래스에 따라 다르게 행동할 수 있음

- 서로 다른 클래스에 속한 객체들이 동일한 메세지에 다른 방식으로 응답할 수 있음

- 파이썬에는 오버로딩은 없음

- **메서드 오버라이딩**
  
  - 상속받은 메서드를 재정의
    - 부모에서 정의한 메서드를 자식에서 변경
    - 부모의 메서드 이름과 기능은 그대로 사용하지만, **특정 기능** 바꾸고 싶을 때
  - 상속 받은 클래스에서 같은 이름의 메서드를 덮어 씀
    - 부모의 메서드를 실행시키고 싶을 때는 super 사용
  
  ```python
  class Person:
      def __init__(self, name):
          self.name = name
  
      def talk(self):
          print(f'{self.name}입니다.')
  ```

# 자식 클래스 1

  class Professor(Person):
      def talk(self):
          print(f'{self.name}일세.') # 오버라이딩 / 덮어 쓰기

# 자식클래스 2

  class Student(Person):
      def talk(self):
          super().talk()   # super() 사용해서 부모클래스 메서드 가져오기
          print(f'저는 학생입니다.')

  p1 = Professor('김교수')
  p1.talk() 
  #김교수일세.

  s1 = Student('이학생')
  s1.talk()

# 

  이학생입니다.
  저는 학생입니다.

```
---

## 캡슐화

---

- 객체의 일부 구현 내용에 대해 외부로부터의 직접적인 액세스를 차단

- 암묵적으로 존재, 언어적으로 존재하지 않음

- 접근 제어자 종류

- Public Acces Modifier
- Protected Acces Modifier
- Private Acces Modifier
- Public Member

- 언더바 없이 시작하는 메서드나 속성
- 어디서나 호출 가능
- 일반적으로 작성되는 메서드나 속성의 대부분
- 하위 클래스 오버라이드 override 허용

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

**# Person 클래스의 인스턴스인 p1은 name 과 age 모두 접근 가능**
p1 = Person('김싸피', 30)
print(p1.name) # 김싸피
print(p1.age) # 30
```

- Protected Member
  
  - 언더바 1개로 시작하는 메서드나 속성
  - 직접 접근 가능하지만, 암묵적 규칙에 의해 부모, 자식 클래스에서만 호출 가능
  - 하위 클래스 오버라이드 override 허용
  
  ```python
  class Person:
      def __init__(self, name, age):
          self.name = name
          self._age = age
  
      def get_age(self):
          return self._age
  
  **# get_age 메서드를 활용하여 호출 가능**
  p1 = Person('김싸피', 30)
  print(p1.get_age()) # 30
  
  # _age 에 직접 접근하여 확인 가능은 하다.. 
  print(p1._age) # 30
  ```

- Private Member
  
  - 언더바 2개로 시작하는 메서드나 속성
  - 본 클래스 내부에서만 사용 가능
  - 하위 클래스 상속 및 호출 불가능 (오류)
  - 외부 호출 불가능 (오류)
  
  ```python
  class Person:
      def __init__(self, name, age):
          self.name = name
          self.__age = age
  
      def get_age(self):
          return self.__age
  
  **# get_age 메서드를 활용하여 호출 가능**
  p1 = Person('김싸피', 30)
  print(p1.get_age()) # 30
  
  # __age 에 직접 접근 불가능!
  print(p1.__age) 
  # AttributeError: 'Person' object has no attribute '__age'
  ```

- getter 메서드 / setter 메서드
  
  - 변수에 접근 할 수 있는 메서드를 별도로 생성
  - getter : 변수 값 읽는 메서드
    - @property 데코레이터 사용
  - setter : 변수의 값을 설정하는 성격의 메서드
    - @변수.setter 사용
  
  ```python
  class Person:
      def __init__(self, age):
          self._age = age
  
      @property
      def age(self):    # 인스턴스 생성 / 나이에 접근 가능
          return self._age
  
      @age.setter   # age 변수 값 설정
      def age(self, new_age):
          if new_age <= 19:  # 19 이하는 노노
              raise ValueError('Too Young For SSAFY')  # raise -> 에러 발생
              return
                  self._age = new_age
  
  p1 = Person(20)
  print(p1.age) # 20
  
  p1.age = 33 
  print(p1.age) # 33   # 값을 변경해도 정상적으로 반환
  
  p1.age = 18
  print(p1.age) # ValueError: Too Young For SSAFY
  ```

---

## 에러 / 예외 처리 Error / Exception Handling

---

- 버그란?
  
  - 소프트웨어에서 발생하는 문제

- 디버깅
  
  - 잘못된 프로그램 수정하는 것
  - 에러 메세지가 발생하는 경우
    - 해당 위치를 찾아 메시지 해결
  - 로직 에러 발생하는 경우
    - 명시적 에러 메시지 없이 예상과 다른 경우
      - 정상 동작 코드 이후의 코드 생각..
      - 전체 코드 다시 보기..
      - 휴식..
  - print 함수 활용

---

- 문법 에러 Syntax Error
  
  - 실행 되지 않음
  
  - 파일 이름, 줄 번호, ^ 문자를 통해 문제 발생 위치 표현
  
  - 줄에서 가장 먼저 에러 감지된 곳 ^ 기호
  
  - **Invalid syntax**
    
    - 문법 오류
  
  - **assign to literal**
    
    - 잘못된 할당
  
  - **EOL** - End of Line
    
    - 괄호 안닫으면
  
  - **EOF** - End od File

---

- 예외 Exception
  
  - 실행 도중 예상치 못한 상황 → 실행 멈춤
    
    - 문장이나 표현식이 문법적으로 맞더라도 발생
  
  - 실행 중에 감지되는 에러
  
  - 여러 타입으로 나타나고, 타입이 메세지 일부로 출력
  
  - 모든 내장 예외는 Exception Class 를 상속받아 이뤄짐
  
  - 사용자 정의 예외 만들어서 관리 가능
  
  - **ZeroDivisionError**
    
    - 0으로 나눌 수 없음
  
  - **NameError**
    
    - namespace 상에 이름이 없는 경우
  
  - **TypeError**
    
    - 타입 불일치
    - argumet 누락 / 개수 초과
    - argument type 불일치
  
  - **ValueError**
    
    - 타입은 올바르나 값이 적절하지 않거나 없는 경우
  
  - **IndexError**
    
    - 인덱스가 존재하지 않거나 범위를 벗어난 경우
  
  - **KeyError**
    
    - 키가 존재하지 않을 경우
  
  - **ModuleNotFoundError**
    
    - 해당 모듈을 찾지 못함
  
  - **ImportError**
    
    - 모듈은 있지만, 존재하지 않는 클래스 / 함수를 가져오는 경우
  
  - **KeyboardInterrupt**
    
    - 임의로 프로그램을 종료했을 때
  
  - **IndentationError**
    
    - 띄어쓰기 Indentation 이 적절하지 않은 경우
  
  ![파이썬 빌트인-내장 예외.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/bf0a1e2c-0387-464b-8ec8-70fd42861179/%ED%8C%8C%EC%9D%B4%EC%8D%AC_%EB%B9%8C%ED%8A%B8%EC%9D%B8-%EB%82%B4%EC%9E%A5_%EC%98%88%EC%99%B8.png)

---

- 예외 처리
  
  - try / except 를 이용하여 예외 처리
    
    ![오류처리.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2dfc057e-9479-42dd-b74d-851bdce29656/%EC%98%A4%EB%A5%98%EC%B2%98%EB%A6%AC.png)
  
  - **try 문**
    
    - 오류가 발생할 가능성이 있는 코드 실행
    - 발생하지 않으면, except 없이 실행 종료
  
  - **except 문**
    
    - 예외가 발생하면 except 실행
    - 예외 상황 처리 코드를 받아서 조치
  
  ```python
  try:
      num = input('숫자 입력 :')
      print(int(num))
  except ValueError:  
      print('숫자가 입력되지 않았습니다.')
  ```
  
  - **as** 키워드를 이용하여 원본 에러 메시지 사용
    - 예외를 다른 이름에 대입
  
  ```python
  try:
      empty_list = []
      print(empty_list[-1])
  except IndexError as err:
      print(f'{err}, 오류가 발생했습니다.') 
  
  # list index out of range, 오류가 발생했습니다.
  ```
  
  - **else**
    - try문에서 예외가 발생하지 않으면 실행
  - **finally**
    - 예외 발생 여부와 관계없이 항상 실행
  - 예시
  
  ```python
  **** 발생 가능 에러 괄호에 모두 명시**
  try:
      num = input('숫자 입력 :')
      100/int(num)
  except (ValueError, ZeroDivisionError):  
      print('제대로 입력해줘')
  
  **** 별도 에러처리 -> 순차 수행이기 때문에 작은 범주부터 예외 처리!!**
  try:
      num = input('숫자 입력 :')
      100/int(num)
  except ValueError:  
      print('숫자를 입력해주세요')
  except ZeroDivisionError:
      print('0으로 나눌 수 없습니다.')
  except:
      print('에러는 모르겠지만 에러가 발생하였습니다.')
  ```
