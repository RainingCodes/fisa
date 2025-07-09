# 250703 파이썬 5일차

### 파이썬 문법 중 몰랐던 문법
1. 부모 클래스 함수를 overriding 할때
```python
def __init__(self, additional: bool = False, *args, **kwargs):
        super().__init__(*args, **kwargs)
        self.additional = additional
```
* 부모 호출시 super() 이용
* *args, **kwars를 이용해서 부모 parameter들을 몰라도 상속해서 이용가능

2. 비교 가능한 객체 만들기
```python
    def __lt__(self, other):
        return self.something < other.something

    def __le__(self, other):
        return self.something <= other.something

    def __gt__(self, other):
        return self.something > other.something

    def __ge__(self, other):
        return self.something >= other.something

    def __eq__(self, other):
        return self.something == other.something
```
* 객체를 부등호, 등호로 비교할 때 기준을 위와 같이 해주면 오버라이딩 된 함수를 기준으로 동작