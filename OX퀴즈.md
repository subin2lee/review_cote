## ⌜문제 설명⌟
### 덧셈, 뺄셈 수식들이 'X [연산자] Y = Z' 형태로 들어있는 문자열 배열 quiz가 매개변수로 주어집니다. 수식이 옳다면 "O"를 틀리다면 "X"를 순서대로 담은 배열을 return하도록 solution 함수를 완성해주세요.

```python
def solution (quiz) :
    
    result_list = []
    for expression in quiz :
        list = expression.split(" ")   #list[0]의 자료형은 string임.. 계산할 수 있게 바꿔야함
        X = list[0]
        Y = list[2]
        Z = list[4]

        if int(X) + int(Y) == int(Z) :   #식 계산
            result_list.append("O")
        
        elif int(X) - int(Y) == int(Z) :    #식 계산
            result_list.append("O")

        else :           #if문 만족안하면
            result_list.append("X")
    
    return result_list

quiz = ["19 - 6 = 13", "5 + 66 = 71", "5 - 15 = 63", "3 - 1 = 2"]
print(solution(quiz))
```

## ☻ 내가 몰랐던 것들 ☺︎
* 몰랐던 문법은 없음
-------
* 접근 방식을 생각하는데 오래 시간이 걸림.
## ☆ 문제 접근 방식 ★
1. for문 이용하여 리스트 속 값들을 각각 뽑아준 다음 공백들을 제거해준다.
<br> &nbsp;&nbsp;&nbsp; ✔︎ expression에 수식들이 할당됨
<br> &nbsp;&nbsp;&nbsp; ✔︎ expression에 할당된 수식들을 split()을 이용하여 공백단위로 쪼개준 다음 리스트로 반환해준다.

```python
for expression in quiz :
    print(expression)
    list = expression.split(" ")
    print(list)

#이렇게 하면 print값으로 아래의 값과 같이 찍힘
# 19 - 6 = 13
# ['19', '-', '6', '=', '13']
# 5 + 66 = 71
# ['5', '+', '66', '=', '71']
# 5 - 15 = 63
# ['5', '-', '15', '=', '63']
# 3 - 1 = 2
# ['3', '-', '1', '=', '2']
```

2. 그럼 각 숫자들의 인덱스를 뽑아준다.
<br> &nbsp;&nbsp;&nbsp; ✔︎ 첫번째 숫자의 값을 할당해줄 X라는 변수를 만들어준다. -> 첫번째 숫자는 각 인덱스의 0번째이므로 **list[0]** 으로 할당해준다.
<br> &nbsp;&nbsp;&nbsp; ✔︎ 두번째 숫자의 값을 할당해줄 Y라는 변수를 만들어준다. -> 두번째 숫자는 각 인덱스의 2번째이므로 **list[2]** 으로 할당해준다.
<br> &nbsp;&nbsp;&nbsp; ✔︎ 세번째 숫자의 값을 할당해줄 Z라는 변수를 만들어준다. -> 세번째 숫자는 각 인덱스의 4번째이므로 **list[4]** 으로 지정해준다.

3. X와 Y를 계산하여 Z와 값이 맞는지 확인해야 하기 때문에 조건문 3개를 작성해준다. (그런데 숫자들을 연산해야 하기 때문에 int()을 이용하여 정수형으로 바꿔준다.)
<br> &nbsp;&nbsp;&nbsp; ✔︎ 첫번째 조건문 : X와 Y를 더해서 Z의 값과 같다면 빈 리스트에 "O" 추가해주기.
<br> &nbsp;&nbsp;&nbsp; ✔︎ 두번째 조건문 : X와 Y를 뺴서 Z의 값과 같다면 빈 리스트에 "0" 추가해주기.
<br> &nbsp;&nbsp;&nbsp; ✔︎ 세번째 조건문 : 위에 두 개의 조건문을 만족하지 않는다면 빈 리스트에 "X" 추가해주기.
