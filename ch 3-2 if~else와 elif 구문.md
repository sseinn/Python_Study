### else 조건문 활용

###### 예제 - if 조건문에 else 구문 추가해서 짝수인지 홀수인지 구분하기

```
# 입력을 받습니다. 
number = input("정수 입력> ")
number = int(number)

# 조건문을 사용합니다.
if number % 2 == 0:
    # 조건이 참일 때, 즉 짝수 조건
    print("짝수입니다")
else:
    # 조건이 거짓일 때, 즉 홀수 조건
    print("홀수입니다")
```

- 실행 결과
```
정수 입력> 13
홀수입니다
```

### elif 구문
세 개 이상의 조건을 연결해서 사용해야 할 때 elif 구문을 이용한다. 

##### 예제 - 계절 구하기
```
# 날짜/시간과 관련된 기능을 가져옵니다.
import datetime

# 현재 날짜/시간을 구하고
#쉽게 사용할 수 있게 월을 변수에 저장합니다.
now = datetime.datetime.now()
month = now.month

# 조건문으로 계절을 확인합니다. 
if month <= month <= t:
    print("현재는 봄입니다.")

elif 6 <= month <= 8:
    print("현재는 여름입니다.")

elif 9 <= month <= 11:
    print("현재는 가을입니다.")

else:
    print("현재는 겨울입니다.")
```

- 실행 결과
```
현재는 가을입니다.
```

### False로 변환되는 값

if 조건문의 매개변수가 불이 아닌 다른 값이 올 때는 자동으로 이를 불로 변환해서 처리해야한다. 
따라서 어떤 값이 True로 변환되고, 어떤 값이 False로 변환되는지 알고 있어야 코드를 이해할 수 있다. 

False로 반환되는 값은 None, 숫자 0,0.0, 빈 컨테이너(빈 문자열, 빈 바이트열, 빈 리스트, 빈 튜플, 빈 딕셔너리 등)이다. 

이 외는 모두 True로 변환된다. 

##### 예제 - False로 변환되는 값

```
print("# if 조건문에 0 넣기")
if 0:
    print("0은 True로 변환됩니다")
else:
    print("0은 False로 변환됩니다")
    print()

print("# if 조건문에 빈 문자열 넣기")

if "":
    print("빈 문자열은 True로 변환됩니다")
else:
    print("빈 문자열은 False로 변환됩니다")
```

- 실행 결과
```
# if 조건문에 0 넣기
0은 False로 변환됩니다

# if 조건문에 빈 문자열 넣기
빈 문자열은 False로 변환됩니다
```

### pass 키워드

if 조건문 사이에는 무조건 들여쓰기 4칸을 넣고 코드를 작성해야만 구문이 성립된다. 아니면 **Indentation Error**가 발생한다. 

```
IndentationError: expected an indented block after 'if' statement on line 6
```


##### 예제 - pass 키워드를 사용한 미구현 부분 입력
```
# 입력을 받습니다. 
number = input("정수 입력> ")
number = int(number)

# 조건문 사용
if number > 0:
    # 양수일 때 아직 미구현 상태입니다. 
    pass
else :
    # 음수일 때 아직 미구현 상태입니다.
    pass
```

pass 키워드를 만나면 '진짜로 아무것도 안함' 또는 '곧 개발하겠음'이라는 의미로 생각하면 된다. 

### raise NotImplementedError

raise 키워드와 미구현 상태를 표현하는 NotImplementedError를 조합해서 raise NotImplementedError를 사용하면 "아직 구현하지 않은 부분이에요!"라는 오류를 강제로 발생시킬 수 있다.

```
# 입력을 받습니다. 
number = input("정수 입력> ")
number = int(number)

# 조건문 사용
if number > 0:
    # 양수일 때 아직 미구현 상태입니다. 
    raise NotImplementedError
else :
    # 음수일 때 아직 미구현 상태입니다.
    raise NotImplementedError
```

- 실행 결과
```
정수 입력> 2
Traceback (most recent call last):
  File "c:\", line 8, in <module>
    raise NotImplementedError
NotImplementedError
```

코드를 실행하면 코드의 실행은 정상적으로 진행된다. 대신 구현되지 않은 부분에 들어서는 순간 NotImplementedError라는 오류를 발생시킨다. 
따라서 구현이 안되었구나라는 걸 인지할 수 있다. 


