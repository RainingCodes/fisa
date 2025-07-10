# 250708 파이썬 5일차

### 파이썬 문법 중 몰랐던 문법
1. 정규식
* match() : <b>처음</b>부터 매치 되는지 조사
* search() : 검색하여 매치되는지 조사
* findall() : 일치하는 모든 문자열(substring) list로 반환
* finditer() : 일치하는 모든 문자열(substring), iteration으로 반환
* 예제
    ```python
    emails = ['python@mail.example.com', 'python+kr@example.com',          # 올바른 형식
          'python-dojang@example.co.kr', 'python_10@example.info',         # 올바른 형식
          'python.dojang@e-xample.com',                                    # 올바른 형식
          '@example.com', 'python@example', 'python@example-com']          # 잘못된 형식


        # 이메일 형식을 판별하는 검사기
        for email in emails:
            p1 = re.compile('@')
            p3 = re.compile(r'\.')
            if len(p1.findall(email)) != 1:
                print('@ 개수 이상')
            else:
                p2 = re.search(r'(\S+)@(\S+)', email)
                if p2 := re.search(r'(\S+)@(\S+)', email):
                if len(p3.findall(domain := p2.group(2))) <= 0:
                    print("도메인 이상")
                else:
                    print('username:',p2.group(1), '\tdomain:', domain)
                else:
                print("도메인 없음")
    ```
2. 문자열 출력
* f-string
* format (key value 처럼 지정해서 할 수 있음)
* % (float, int간 형변환 가능)
* 예제
    ```python
    print(f'{10:10d}') # default 오른쪽 정렬
    print(f'{10:<5d}') # 왼쪽 정렬'
    print(f'{10:^10d}') # 가운데 정렬
    ```
    ![](https://i.imgur.com/bNNHe6L.png)

2. 파일쓰기 (in colab)
```python
%%writefile /content/drive/MyDrive/fisa/package/math1.py

def add(x, y):
    return x+y

def minus(x, y):
    return x-y

PI = 3.14
```
* 저 위치에 math1.py 파일 생성됨

3. 예외처리
```python
try:
  f = open('testex.txt', 'r')
  print('file?')
except FileNotFoundError as e:
  f = open('testex.txt', 'w')
  f.write('hi')
  f.close()
else: # except 안걸리고 넘어오는 곳
  while line := f.readlines():
    print(line)
  print('file execution')
finally:
  f.close()
  print('file closed')
```
* else는 except에 안걸리는 try에서 성공하면 실행
* finally는 모두 실행

4. 클래스
```python
class Car:
  name = '기본'
  year = 2000
  color = 'yellow'
  n = 0 

  def __init__(self):
    Car.n += 1 


  def introduce(self):
    print(f'차이름: {self.name}, 생산년도: {self.year}, 차색깔: {self.color}')
  
  @classmethod 
  def introduce2(cls): 
    print(f'현재 {cls.n} 대의 차량을 판매 중입니다.')

모닝 = Car()
모닝.name
모닝.introduce()
Car.introduce2()


페라리 = Car()
Car.introduce2()
```
![](https://i.imgur.com/LVb6zjB.png)
* 다른 언어들에서 정적으로 변수를 관리하는 건 익숙한데 python도 그와 비슷하게 다루기 위한 문법이 있다.
* 다만 완벽하게 다른 언어처럼 엄격하게 객체, instance 관리가 되는 건 아니다.
