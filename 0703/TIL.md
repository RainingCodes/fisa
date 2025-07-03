# 250703 파이썬 2일차

### 파이썬 문법 중 몰랐던 문법
1. 파이썬의 철학을 확인할 수 있는 명령어
```python
import this
```
* 철학을 라이브러리에 담아두다니... 너무 신기

2. digit vs decimal vs numeric

```python
a = '1234' # 타입이 str이지만 온전히 숫자만 가지고 있다면 True를 반환
b = '1/2'
e = '3²'
f = '-1'
g = '½'

print('isdigit()') # 문자열의 모든 문자가 숫자(0-9)이면 True를 출력
print(a.isdigit()) # True
print(b.isdigit()) # False
print(e.isdigit()) # True
print(f.isdigit()) # False '-1' 은 '-'가 음수이기 때문에
print(g.isdigit()) # False

print('isdecimal() - 특수문자는 숫자로 취급하지 않음')
print(a.isdecimal()) # True
print(b.isdecimal()) # False
print(e.isdecimal()) # False
print(f.isdecimal()) # False
print(g.isdecimal()) # False

print('isnumeric() -  문자열의 모든 문자가 숫자(분수, 아래 첨자, 위 첨자 등의 다른 숫자도 포함)')
print(a.isnumeric()) # True
print(b.isnumeric()) # False
print(e.isnumeric()) # True
print(f.isnumeric()) # False
print(g.isnumeric()) # True
```
* 음수, 소숫점은 특수문자로 인식해 이러한 함수들로 판단 불가
* 숫자로 된 건지 파악하려는 용도로 주로 사용하는 용도임

3. match~case 문
```python
a = input('기분이 좋나요? (y or n)')
match a.split():
  case ['Y'|'y'|'yes', *others]: # |는 or로 동작
    print('좋군요')
  case _: # else --> 나머지 모든 것을 의미함 와일드 카드로 값을 무시할 때 이용, default 키워드 사용 가능
    print('아쉽군요.', _)
```
* Python 3.10 부터 지원하는 연산자 (이전 파이썬 컴파일러에선 오류 날 수 있음)

4. \* (for packing)

```python
a = [1, 2, 3, 4, 5]
b, c, *d = a
print(b, c, d) # 1 2 [3, 4, 5]

```
* 여러개 처리를 packing(unpacking 포함) 할때 이용

5. walrus operator (바다코끼리 연산자)
```python
listA = [1, 2, 3, 4, 5]
if((n := len(listA)) > 3):
    print('listA의 길이가 3보다 큽니다. 현재 listA 길이', n)

```
* Python 3.8부터 지원하는 연산자
* 할당 + return 
* 위의 예처럼 할당하고 할당된 변수를 다시 이용할 때 편함

6. 파이썬 인터프리터에 있는 매직 keyword 
```python
%%time
for i in range(10):
  print('hi')
```
![](https://i.imgur.com/f309ix0.png)
* 해당 쉘의 실행시간을 보여줌