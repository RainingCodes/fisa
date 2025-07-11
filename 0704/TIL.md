# 250704 파이썬 3일차

### 파이썬 문법 중 몰랐던 문법
1. 함수 가변인자
```python
def func1(*args):
    print(args)
func1(1, 2, 3, 4, 5) # 출력 (1, 2, 3, 4, 5)
```
* 여러 개 넘겨주는 설정 가능
```python
def func2(**kwargs):
    print(kwargs)
func2(greeting="hello", name="aaa")
```
* key와 value 형태로 갯수 미정일 경우
2. decorator
```python
import time

def timer(func): # 함수를 인자로 받아서 실행합니다.
    def wrapper():
        start_time = time.time()
        func() # func()을 호출하기 전후로 작업을 합니다.
        end_time = time.time()
        print("total time: ", end_time - start_time) # 끝나는 시간
    return wrapper

@timer
def say_hello():
    time.sleep(5)
    print("Hello!")
```
* func() 라는 걸로 wrapping하는 함수를 대신하게 하는 것이 신기했음
---
* 파이썬 코드들에서 보기만 했던 문법들이 구체적인 사용방법을 알게 되었다.