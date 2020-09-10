jupyter cell 단축키

cell

a, b, d

ctrl + enter : 현재 cell을 실행



numpy : Numerical Python



vector와 matrix 연산에 특화

pandas, Matplotlib의 기반이 되는 module

machine, deep learning에서 많이 사용



ndarray라고 불리는 n-차원의 배열을 제공



ndarray특징 :

python의 list와 유사

같은 데이터타입만 저장가능

dtype

a[0]

type(a)

type(a[0])

np.array(a, dtype = np.float64)



arr.ndim 차원의 개수

arr.shape =()

astype

zeros, ones, full, empty(초기화없이 공간만, 속도가빠르다.)

arange

linspace

copy

plot matplotlib.pyplot as plt

mean=50, std=2

random.nomal(mean,std,(10000, ))

plt.hist(arr,bins=100)

plt.show()

랜덤 관련 함수

1. 난수의 재현
   seed
2. ndarray의 순서를 랜덤하게 변경
   random.shuffle(arr)
3. ndarray안에서 무작위로 선택 sapling기능
   random.choice(arr, size, replace, p)



reshape

ravel



reshape, resize는 리턴값을 받지않는다.

for in enumerate()

arr[1: -1:2]

boolean indexing

np.ix_()



행렬 곱연산

np.dot(), npmatmul()로 수행

두 행렬의 열 vector와 행 Vector의 size가 같아야함

transpose

T

iterator

비교연산(전체와 인덱스)

np.sum(), np.cumsum(), np.mean(), np.min(), np.argmax(arr), argmin, np.std(), np.exp(arr), np.log10(arr)

numpy의 모든 집계함수는 axis를 기준으로 계산