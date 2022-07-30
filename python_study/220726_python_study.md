- 소금물 농도 / 입력 최대 5번 / 중간에 Done 입력시 출력하러~

```python
n = 1
salt_lst = []
water_lst = []

while n <= 5:  # 입력은 최대 5개
    x = input('소금물의 농도(%)와 소금물의 양(g)을 입력하십시오:')
    if x == 'Done':  # 'Done'입력 시 그만 입력
        break
    else:
        salt, water = x.split()  # 공백 기준으로 찢어서 각 변수에 저장
        salt = float(salt.strip('%'))  # '%' 잘라주기
        water = float(water.strip('g'))  # 'g' 잘라주기
    salt_lst.append(salt * water)  # 소금 무게 리스트에 추가
    water_lst.append(water)  # 물 무게 리스트에 추가
avrg = round(sum(salt_lst)/sum(water_lst),2)  # 소수 반올림해서 두자리까지 출력
new_water = sum(water_lst)

print(f'{avrg}% {new_water}g')
```

---

- 요소 합 구하기

```python
def sum_list(numbers):

    total = 0
    for i in numbers:
        for j in i:
            total += j
    return total

if __name__ == '__main__':
    print(sum_list([[1, 4], [10, 5], [20, 30]]))
```

```python
def sum_list_index(numbers):

        s = 0
    for i in range(len(numbers)):
        for j in range(len(numbers[i])):
            s += numbers[i][j]
    return s

if __name__ == '__main__':
    print(sum_list_index([[1, 4], [10, 5], [20, 30]]))
```

```python
def sum_list_while(numbers):

    s = 0
    i = 0
    while i < len(numbers):
        j = 0
        while j < len(numbers[i]):
            s += numbers[i][j]
            j += 1
        i += 1
    return s

if __name__ == '__main__':
    print(sum_list_while([[1, 4], [10, 5], [20, 30]]))
```

---

- 합 구하기

```python
students = [
 [100, 80, 100],
 [90, 90, 60],
 [80, 80, 80]
]

for i in students:
    total = 0
    for j in i:
        total += j
    print(total)
# 280
# 240
# 240
```

---

- 순회 (열/ 행)

```python
l = [
  [1, 2, 3],
  [4, 5, 6], 
  [7, 8, 9]
]
print('행 우선')
for i in range(len(l)):
    for j in range(len(l[i])):
        print(l[i][j], end=' ')
    print()

print('열 우선')
for i in range(len(l)):
    for j in range(len(l[i])):
        print(l[j][i], end=' ')
    print()
#
행 우선
1 2 3 
4 5 6 
7 8 9 
#
열 우선
1 4 7 
2 5 8 
3 6 9
```

---

- 알파벳… 있어..? 그럼 리스트로 줘.. 없으면 -1 로…

```python
def my_find(text, alphabet):

    lst = []
    for i in range(len(text)):
        if text[i] == alphabet:
            lst.append(i)
    return lst if lst else -1
# 설명이 필요..

if __name__ == '__main__':
    print(my_find('apple', 'p'))  # [1, 2]
    print(my_find('a', 'p'))  # -1
```

---

- 학생은 n 명.. students는 결석자..! 그럼 출석한 사람은..? `출력 예시: 2 4 6 7`

```python
def check(n, students):

    lst = list(range(1,n+1))
    students_num = list(map(int, students.split()))
    result = ''

    for i in lst:
        if i not in students_num:
            result += str(i)
    return ' '.join(result)

if __name__ == '__main__':
    print(check(7, '1 3 5')) # 2 4 6 7
```

---

- 과일..? Fxxx ‘rotten’ 그리고.. 싹 다 소문자로 줘..

```python
def change_rotten_fruit(fruit_bag):

    new_bag = []
    for i in fruit_bag:
        i = i.lstrip('rotten')
        i = i.lower()
        new_bag.append(i)
    return new_bag

if __name__ == '__main__':
    print(change_rotten_fruit(['apple', 'rottenBanana', 'apple'] ))
    print(change_rotten_fruit(['rottenapple', 'rottenBanana', 'apple', 'rottenGrape']))

# ['apple', 'banana', 'apple']
# ['apple', 'banana', 'apple', 'grape']
```

---

- 이거 아니면 이걸로 줘 ( return 문을 봐라 )

```python
ex) 입력된 수가 짝수라면 2로 나눈다.
입력된 수가 홀수라면 3을 곱하고 1을 더한다.
결과로 나온 수에 같은 작업을 1이 될 때까지 반복한다.
몇번 걸렸는가 출력! 
단, 500번이 넘어가면 -1로 출력 부탁!!

def collatz(num):

    cnt = 0
    while num != 1:
        if num % 2 == 0:
            num = num/2
        else:
            num = (num*3)+1
        cnt += 1

    return cnt if cnt < 500 else -1
# cnt값을 리턴할 건데, 500 이상이라면, 그냥 -1로 줘라

if __name__ == '__main__':
    print(collatz(6)) # 8
    print(collatz(16)) # 4
    print(collatz(27)) # 111
    print(collatz(626331)) # -1
```

---

- 딕셔너리 뒤집기!

```python
def dict_invert(my_dict):

    new_dict = {}
    for key,value in my_dict.items():
        new_dict[value] = new_dict.get(value, []) + [key] 
# value를 키로 가지는 new_dict / 그 밸류 값은 ?
# new_dict.get(value, []) -> 밸류값 없으면 []를 디폴트로 나둬라
# 그 디폴트 값 []공간에 [key]가 들어감
    return new_dict

if __name__ == '__main__':
    print(dict_invert({1: 10, 2: 20, 3: 30})) # {10: [1], 20: [2], 30: [3]}
    print(dict_invert({1: 10, 2: 20, 3: 30, 4: 30})) # {10: [1], 20: [2], 30: [3, 4]}
    print(dict_invert({1: True, 2: True, 3: True})) # {True: [1, 2, 3]}
```

---
- sys.stdin.readline()

  - import sys 를 통해 모듈 불러오기
  - input() 처럼 사용

  ```python
  import sys  # sys 모듈 불러오기

  T = int(sys.stdin.readline())  # sys.stdin.readline() 함수 사용 -> input()과 사용 동일..

  for tc in range(T):
      a,b = map(int, sys.stdin.readline().split())
      print(a + b)
  ```

  - sys.stdin.readline()과 input()은 같은 역할을 하지 않음
    - input() 내장 함수는 parameter로 prompt message를 받을 수 있음

      입력 받기 전 prompt message를 출력해야 함 ( 없는 경우도 있음 )

      input() 내장 함수는 입력받은 값의 개행 문자를 삭제시켜서 리턴

      ( 입력받은 문자열에 rstrip() 함수를 적용시켜서 리턴 )

    - sys.stdin.readline()은 prompt message를 인수로 받지 않음

      개행 문자를 포함한 값을 리턴


---

- 리스트 중간에 값 삽입

```python
lst = [1,2,3,4,5]
lst[2:2] = [10,11,12]
print(lst1)
# [1, 2, 10, 11, 12, 3, 4, 5]

# 위와 같은 결과
lst = [1,2,3,4,5]
lst = lst[0:2] + [10,11,12] + lst[2:]
print(lst)
```

---

- .sort() 와 sorted() 차이
  
  - 리스트명.sort() 는 `리스트형의 메소드`
  - sorted(리스트명) 형식으로 `내장함수`
  
  ```python
  a1 = [6, 3, 9]
  print('a1:', a1)
  a2 = a1.sort() # 원본을 정렬하고 수정합니다(in-place)
  print('-----정렬 후-----')
  print('a1:', a1)
  print('a2:', a2)
  
  #
  a1: [6, 3, 9]
  -----정렬 후-----
  a1: [3, 6, 9]
  a2: None
  ```
  
  ```python
  b1 = [6, 3, 9]
  print('b1:', b1)
  b2 = sorted(b1) # 원본은 유지하고 정렬한 새 리스트를 만듭니다
  print('-----정렬 후-----')
  print('b1:', b1)
  print('b2:', b2)
  
  # 
  b1: [6, 3, 9]
  -----정렬 후-----
  b1: [6, 3, 9]
  b2: [3, 6, 9]
  ```

---

- .extend() 와 .append() 차이
  
  ```python
  .extend() 리스트에 iterable(list, range, tuple, str) 값을 붙일 수 있음   
  
  cafe = ['starbucks', 'tomntoms', 'hollys']
  cafe.extend(['wcafe','빽다방']) # cafe += ['wcafe','빽다방']
  print(cafe)
  #
  ['starbucks', 'tomntoms', 'hollys', 'wcafe', '빽다방']
  
  cafe.extend('ediya')
  print(cafe)
  #
  ['starbucks', 'tomntoms', 'hollys', 'wcafe', '빽다방', 'e', 'd', 'i', 'y', 'a']
  ```
  
  ```python
  .append() 리스트에 값을 추가 할 수 있음   
  
  cafe = ['starbucks', 'tomntoms', 'hollys']
  cafe.append('banapresso')
  print(cafe) 
  #
  ['starbucks', 'tomntoms', 'hollys', 'banapresso']
  
  cafe.append(['coffeenie'])
  print(cafe)
  #
  ['starbucks', 'tomntoms', 'hollys', 'banapresso', ['coffeenie']]
  ```

---

- 더하기..!!!!
  
  ```python
  print(sum(map(int,'12345')))
  # 15
  ```

---

- Math.ceil() 함수
  
  - 주어진 숫자보다 크거나 같은 숫자 중 가장 작은 숫자를 integer 로 반환
  
  ```python
  Math.ceil(x)
  
  Math.ceil(.95);    // 1
  Math.ceil(4);      // 4
  Math.ceil(7.004);  // 8
  Math.ceil(-0.95);  // -0
  Math.ceil(-4);     // -4
  Math.ceil(-7.004); // -7
  ```

---

- 이거 아니면 이걸로 줘 ( return 문을 봐라 )
  
  ```python
  ex) 입력된 수가 짝수라면 2로 나눈다.
  입력된 수가 홀수라면 3을 곱하고 1을 더한다.
  결과로 나온 수에 같은 작업을 1이 될 때까지 반복한다.
  몇번 걸렸는가 출력! 
  단, 500번이 넘어가면 -1로 출력 부탁!!
  
  def collatz(num):
  
      cnt = 0
      while num != 1:
          if num % 2 == 0:
              num = num/2
          else:
              num = (num*3)+1
          cnt += 1
  
      return cnt if cnt < 500 else -1
  # cnt값을 리턴할 건데, 500 이상이라면, 그냥 -1로 줘라
  
  if __name__ == '__main__':
      print(collatz(6)) # 8
      print(collatz(16)) # 4
      print(collatz(27)) # 111
      print(collatz(626331)) # -1
  ```
