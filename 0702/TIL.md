#250702 파이썬 1일차


### 파이썬 문법 중 몰랐던 문법
1. 두 변수의 값을 swap할 때 보통 다른 변수에 그 변수의 주소 or 값을 따로 저장해서 swap하는데
```python
a = 10
b = 20
a, b = b,a # 이렇게 swap이 가능함!
```
* 위의 코드처럼 swap이 가능하다는 사실이 새로웠다.

2. 파이썬 내장 함수를 코드로 확인하는 방법
```python
listA = [1, 2, 3, 4]
print(dir(listA)) # listA.하고 호출할 수 있는 함수들을 list에 담아서 보여줌
```

3. 파이썬 내장 함수를 어떻게 사용하는 지 확인하는 방법
```python

help(listA.count)
```
Help on built-in function count:

count(value, /) method of builtins.list instance
    Return number of occurrences of value.
* 여기서 / 앞에있는건 꼭 넣어주어야 하는 parameter

```python
help(listA.sort) 
``` 
Help on built-in function sort:

sort(*, key=None, reverse=False) method of builtins.list instance
    Sort the list in ascending order and return None.
    
    The sort is in-place (i.e. the list itself is modified) and stable (i.e. the
    order of two equal elements is maintained).
    
    If a key function is given, apply it once to each list item and sort them,
    ascending or descending, according to their function values.
    
    The reverse flag can be set to sort in descending order.
* 여기서 * 뒤에 있는 건 parameter=argument 형식으로만 사용 가능

```python
help(dict.update)
```
Help on method_descriptor:

update(...) unbound builtins.dict method
    D.update([E, ]**F) -> None.  Update D from dict/iterable E and F.
    If E is present and has a .keys() method, then does:  for k in E: D[k] = E[k]
    If E is present and lacks a .keys() method, then does:  for k, v in E: D[k] = v
    In either case, this is followed by: for k in F:  D[k] = F[k]
* 여기서 ...은 여러개 가능

