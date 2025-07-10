# 250703 파이썬 6일차

### numpy 특집
* 배열, 행렬을 다룰 때 유용(ndarray), 수학/과학 연산 지원
1. 브로드캐스팅
```python
score = np.array([10, 20, 30, 40, 50])
score + 10
```
* score의 모든 값에 10씩 더해져서 출력됨
2. 실수 범위형 배열
```python
np.arange(0, 1, 0.1)
```
3. 복소수 (양자, 반도체, 특수 데이터 등등 다룰 때 유용)
```python
np.array([1-2j, 3+j])
```
4. 초기화된 배열 생성
```python
np.zeros((3,2))
np.ones((1,2))
```
* 0이나 1로 초기화된 기본 배열 만들 때 유용
5. 랜덤
```python
np.random.rand(1000) #균등분포로 뽑을 수 있음 --> 시각화 해보면 분포가 거의 정규분포
```
6. 정렬
```python
arr = np.array([3, 8, 4, 1, 6, 9])
np.sort(arr) # 오름차순
-np.sort(-arr) #내림차순 ==> 브로드캐스팅 때문에 이렇게 했을 때 잘 동작
```
7. 배열 내에 조건을 만족하는 것 찾기
```python
x[x>3] #boolean indexing
np.all(x>3), np.all(x<5), np.any(x<5), np.any(x>5)
```
* 브로드캐스팅 덕분에 조건을 만족하는 것을 찾기가 편함
* 모두 만족하는지, 하나라도 만족하는지를 보는 all, any 문법도 있음

