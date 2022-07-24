# 제어문

## 제어문(Control Statement)

: 위 → 아래로 차례로 명령 수행하는 파이썬에서 특정 상황에 코드를 선택적으로 실행(**분기**/**조건**) 하거나 계속 실행(**반복**)하는 제어가 필요

- **순서도**(flowchart)로 작성 가능
    - 

### **조건문(Conditional Statement)**

: 참/거짓 판단하는 조건식과 함께 사용
![image](https://user-images.githubusercontent.com/109324394/180641403-46d6b6b4-6e12-4884-b477-84c797c81f78.png)



- **조건문 기본**
    - 조건 참) 들여쓰기 되어있는 코드 블록 실행
    - 조건 거짓) else 이후 들여쓰기 되어있는 코드 블록 실행 →선택적
    

    - *조건문 실습 문제* - 홀,짝 여부
        
        ```python
        num = int(input())
        if num % 2:
        	print('홀수')
        else:
        	print('짝수')
        ```
        
- **복수 조건문** : elif 조건
    - 복수 조건문 실습 - 미세먼지 농도
        
        ```python
        dust = 80
        if dust > 150:
        	print('매우 나쁨')
        elif dust > 80:
        	print('나쁨')
        elif dust > 30:
        	print('보통')
        elif dust >= 0:
        	print('좋음')
        else:
        	print('입력 오류')
        ```
        

```python
a = 5
if a > 5 :
	print('5 초과')
else:
	print('5 이하')
print(a)

# 5 이하
# 5
```

- **중첩 조건문** : 조건문 안의 조건문
    
    ```python
    if 조건:
    	if 조건2:  # 조건 1 and 조건 2로 해도 됨. 
    else:
    ```
    
- **조건 표현식** (Conditional Expression)
    - 삼향 연산자(Ternary Operator) 로 부르기도 함
    - 일반적으로 조건에 따라 값을 정할 때 활용
        - ②왼 참(True일 때)   ① if 조건 else  ③ 오 거

```python
num = -5
if num > = 0:
	value = num
else:
	value = 0
print(value)
```

```python
value = num if num % 2 else 0
```

 

### **반복문**

: 특정 조건을 만족할 때까지 같은 동작을 계속 반복하고 싶을 때

- 반복문 종류
    - while 문 : 종료 조건에 해당하는 코드를 통해 반복문을 종료시켜야 함 (조건/상황)
    - for 문 : 반복가능한 객체를 모두 순회하면 종료 (조건/횟수)
        
        → 별도의 종료 조건 필요 X 
        
    - 반복 제어 : break, contiue, for-else

### while 문 (참인 동안 반복하기)

: 조건식이 참인 경우 코드 반복 (’참’인 동안 반복하게)

“조건 만족할 때까지 실행하고 싶다면”

→ 참인 경우 들여쓰기 된 코드 블록 실행

→ 코드 블록 실행 후 다시 조건식 검사하여 반복 실행

⇒ 무한루프 하지 않도록 종료조건 필수


```python
a = 0
while a < 5:
	print('a')
	a += 1
print('끝')
```

- **복합 연산자**(In-Place Operator) : 연산 + 할당
    - ex) 반복문 통해 개수 카운트 ⇒ a += 1

### for 문

: *시퀀스를 포함한 순회 가능한 객체(iterable)의 요소를 모두 순회

*시퀀스 : string, tuple, list, range ⇒ 순회가능한 객체(**iterable**)요소 순회

→ 처음 요소부터 끝 요소까지 모두 순회하므로 별도 종료 조건 필요 X

- **iterable**
    - 순회할 수 있는 자료형(string, list, dict, tuple, range, set 등)
    - 순회형 함수(range, enumerate)
    
    <aside>
    💡 for 변수명 in **iterable** :
    
    </aside>
    
- **딕셔너리** : 기본적으로 key를 순회, key 통해 값 활용
    
    → for 문에 넣고 변수만 출력하면 key만 나옴
    
    → print(변수, 딕셔너리[변수]) : 변수는 딕셔너리 내 키를 순회하여 출력, 이후 두번째 딕셔너리[변수]로 딕셔너리[키]가 되므로 [키]에서 키에 해당하는 value가 나옴
    
    - 추가 메서드 활용
        - keys() : key만
        - values() : value만
        - items() : (key, value)의 튜플로

- **enumerate()** =items와 비슷
    - (index, value) 형태로 값 반환
    - 인덱스와 객체를 쌍으로 열거형 객체 반환
        - enumerate(변수, start = 1) —> start 지정하면 해당 값부터 순차적 증가

- **List Comprehension** : 표현식과 제어문을 통해 특정 값 가진 리스트를 간결하게 생성
    - [ code(내가 원하는 방식) for 변수 in iterable ]
    - [ code for 변수 in iterable if 조건식 ]

```python
lst = []
for x in iterable:
	lst.append(x*2)
print(lst)

```

```python
lst = [ x * 2 for x in iterable ]
print(lst)
```

- **Dictionary Comprehension**
    - {key: value for 변수 in iterable}

```python
dict = {} #그냥 중괄호 빈 것은 set 아니고 dict

for num in range(1,4):
	dict[num] = num**3  
#딕셔너리 value 찾을 때처럼 딕[key] = value 해주면 할당
print(dict)

#{1:1, 2:8, 3:27}
```

```python
dict = {num:num**3 for num in range(1,4)}
print(dict)
```

- **반복문 제어**
    - break : 반복문 종료
    - continue : 이후 코드블록 수행 x, 다음 반복 실행
    - for-else : 끝까지 반복문 실행한 이후에 else문 실행
        - for 문에서 해당 안 되면 결과 x, 다음 변수 넣음
        - break를 통해 중간 종료되는 경우 else문 실행x
    - pass : 아무것도 하지 않음
        - 문법적으로 필요없지만 할일이 없을 때
