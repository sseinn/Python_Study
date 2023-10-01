### Boolean (불린, 불리언)

불은 오직 True와 False 값만 가질 수 있다. 

```
>>> print(True)
True
>>> print(False)
False
```

### 불 만들기 : 비교 연산자

불은 비교 연산자를 통해 만들 수 있다.
```
>>> print(10 == 100)
False
>>> print(10 != 100)
True
>>> print(10 < 100)
True
>>> print(10 > 100)
False
>>> print(10 <= 100)
True
>>> print(10 >= 100)
False
```

파이썬은 **문자열**에도 비교 연산자를 적용할 수 있다. 이때 한글은 사전 순저(가나다순)로 앞에 있는 것이 작은 값을 갖는다. 
예를 들어 '가방'과 '하마'를 비교하면 사전 순서로 '가방'이 앞에 있으므로 '가방'이 '하마'보다 작은 값을 갖는다.

```
>>> print("가방" == "가방")
      
True
>>> print("가방" != "가방")
      
False
>>> print("가방" <= "하마")
      
True
>>> print("가방" > "하마")
      
False
```

파이썬은 **변수의 범위**도 비교할 수 있다. 

```
x = 25
      
>>> print(10 < x < 30)
      
True
>>> print(40 < x < 60)
      
False
```

### 불 연산하기 : 논리 연산자

불을 만들 때는 비교 연산자를 사용한다. 그리고 불끼리 논리 연산자를 사용할 수 있다. 

|연산자          |의미                          |설명                         |
|----------------|-------------------------------|-----------------------------|
|`not`            |`아니다`            |'불을 반대로 전환한다.'            |
|`and`           |`그리고`            |`피연산자 두 개가 모두 참일 때 True를 출력하고, 그 외에는 모두 False를 출력한다. `            |
|`or`           |`또는`|`피연산자 두 개 중에 하나만 참이라도 True를 출력하며, 두 개가 모두 거짓일 때만 False를 출력한다 `|

### not 연산자

not 연산자는 단항 연산자로, 참과 거짓을 반대로 바꿀 때 사용한다. 

```
>>> print(not True)
      
False
>>> print(not False)
      
True
```

##### 예제 - not 연산자 조합하기

```
x = 10
under_20 = x < 20 # under_20 = (x < 20)
print("under_20 : ", under_20)
print("not under_20 : ", not under_20)
```

- 실행 결과
```
under_20 :  True
not under_20 :  False
```

### and 연산자와 or 연산자

**and 연산자**

|좌변                |우변                          |결과                    |
|----------------|-------------------------------|-----------------------------|
|`True`|`True`|`True`          |
|`True`          |`False`            |`False`            |
|`False`        |`True`|`False`|
|`False`        |`False`        |`False`|


**or 연산자**

|좌변                |우변                          |결과                    |
|----------------|-------------------------------|-----------------------------|
|`True`|`True`|`True`          |
|`True`          |`False`            |`True`            |
|`False`        |`True`|`True`|
|`False`        |`False`        |`False`|


### if 조건문

###### 예제 - 조건문의 기본 사용
```
# 입력을 받습니다. 
number = input("정수 입력> ")
number = int(number)

# 양수 조건

if number > 0:
    print("양수입니다")

# 음수 조건

if number < 0:
    print("음수입니다")


# 0 조건
if number == 0:
    print("0입니다.")
```

- 실행 결과
```
정수 입력> 23
양수입니다
```

##### 예제 - 날짜/시간 출력하기
```
# 날짜/시간과 관련된 기능을 가져옵니다. 
import datetime

# 현재 날짜/시간을 구합니다.
now = datetime.datetime.now()

# 출력합니다. 
print(now.year, "년")
print(now.month, "월")
print(now.day, "일")
print(now.hour, "시")
print(now.minute, "분")
print(now.second, "초")
```

- 실행 결과
```
2023 년
10 월
1 일
16 시
49 분
29 초
```

1. **모듈**이란 기능을 활용해서 **datetime**이라는 기능을 가져왔다. 
2. **datetime.datetime.now()**란 함수로 현재 시간을 구해 now 변수에 대입한다.
3. now.year(년), now.month(월), now.day(일), now.hour(시), now.minute(분), now.second(초)를 사용해서 현재의 년, 월, 일, 시, 분, 초를 출력한다.

이는 현재 시간을 기반으로 하고 있기 때문에 그 결과는 실행할 때마다 다르다. 

##### 예제 - 날짜/시간을 한줄로 출력하기
```
# 날짜/시간과 관련된 기능을 가져옵니다. 
import datetime

# 현재 날짜/시간을 구합니다.
now = datetime.datetime.now()

# 출력합니다. 
print("{}년 {}월 {}일 {}시 {}분 {}초".format(
    now.year,
    now.month,
    now.day,
    now.hour,
    now.minute,
    now.second
))
```

- 실행 결과
```
2023년 10월 1일 16시 54분 52초
```

대부분 프로그래밍 언어는 월을 0~11까지 출력한다. 

##### 예제 - 오전과 오후를 구분하는 프로그램
```
# 날짜/시간과 관련된 기능을 가져옵니다. 
import datetime

# 현재 날짜/시간을 구합니다.
now = datetime.datetime.now()

# 오전 구분
if now.hour < 12:
    print("현재 시각은 {}시로 오전입니다.!".format(now.hour))

# 오후 구분
if now.hour >= 12:
    print("현재 시각은 {}시로 오후입니다!".format(now.hour))
```

- 실행 결과
```
현재 시각은 16시로 오후입니다!
```

##### 계절을 구분하는 프로그램
```
# 날짜/시간과 관련된 기능을 가져옵니다. 
import datetime

# 현재 날짜/시간을 구합니다.
now = datetime.datetime.now()

# 봄 구분
if 3 <= now.month <= 5:
    print("이번 달은 {}월로 봄입니다!".format(now.month))

# 여름 구분
if 6 <= now.month <= 8:
    print("이번 달은 {}월로 여름입니다!".format(now.month))
          
# 가을 구분
if 9 <= now.month <= 11:
    print("이번 달은 {}월로 가을입니다!".format(now.month))

# 겨울 구분
if 1 <= now.month <= 2 or now.month == 12:
    print("이번 달은 {}월로 겨울입니다!".format(now.month))
```

- 실행 결과
```
이번 달은 10월로 가을입니다!
```

##### 예제 - 끝자리로 짝수와 홀수 구분
```
# 입력을 받습니다. 
number = input("정수 입력> ")

# 마지막 자리 숫자를 추출
last_character = number[-1]

# 숫자로 변환하기
last_character = int(last_character)

# 짝수 확인
if last_character == 0 \
    or last_character == 2 \
    or last_character == 4 \
    or last_character == 6 \
    or last_character == 8 :
    print("짝수입니다")

# 홀수 확인
if last_character == 1 \
    or last_character == 3 \
    or last_character == 5 \
    or last_character == 7 \
    or last_character == 9 :
    print("홀수입니다")
```

- 실행 결과
```
정수 입력> 52
짝수입니다
```


##### 예제 - in 문자열 연산자를 활용해서 짝수와 홀수 구분
```
# 입력을 받습니다. 
number = input("정수 입력> ")
last_character = number[-1]

# 짝수 조건
if last_character in "02468":
    print("짝수입니다")

# 홀수 확인
if last_character in "13579":
    print("홀수입니다")
```

- 실행 결과
```
정수 입력> 52
짝수입니다
```

##### 예제 - 나머지 연산자를 활용해서 짝수와 홀수 구분
```
# 입력을 받습니다. 
number = input("정수 입력> ")
last_character = int(number)

# 짝수 조건
if number % 2 == 0:
    print("짝수입니다")

# 홀수 확인
if number % 2 == 1:
    print("홀수입니다")
```

- 실행 결과
```
# 입력을 받습니다. 
number = input("정수 입력> ")
number = int(number)

# 짝수 조건
if number % 2 == 0:
    print("짝수입니다")

# 홀수 확인
if number % 2 == 1:
    print("홀수입니다")
```

- 실행 결과
```
정수 입력> 53
홀수입니다
```



