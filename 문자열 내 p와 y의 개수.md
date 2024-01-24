## ⌜문제 설명⌟
### 대문자와 소문자가 섞여 있는 문자열 s가 주어집니다. s에 'p'의 개수와 'y'의 개수를 비교해 같으면 True, 다르면 False를 반환하는 solution을 완성하세요. 'p', 'y' 모두 하나도 없는 경우는 항상 True를 반환합니다. 단, 개수를 비교할 때 대문자와 소문자는 구별하지 않습니다.

#### 예를 들어 s가 "pPoooyY"이면 true를 반환하고 "Pyy"라면 false를 반환합니다.

```python
def solution(s) :

    lower_s = s.lower()
    print(lower_s)

    #변수s 속에 있는 p와 y의 개수 알기
    count_p = lower_s.count("p")
    count_y = lower_s.count("y")

    print(count_p)
    print(count_y)

    #p와 y의 개수가 같다면 True (p, y가 없는 경우도 항상 True)
    if count_p == count_y :
        return True
    #p와 y의 개수가 다르다면 False
    elif count_p != count_y :
        return False

s = "pPoooyY"
print(solution(s))
```

## ☻ 내가 몰랐던 것들 ☺︎
[문제 이해를 잘못해서 ㅎㅎ p와 P, y와 Y의 대소문자 상관없이 개수를 비교해야 함]
* lower() - 문자열을 소문자로 바꿔줌
* upper() - 문자열을 대문자로 바꿔줌
* count() - ()안에 개수를 알고 싶은 문자를 넣고, 해당 문자가 얼만큼 있는지 세어줌

## ☆ 문제 접근 방식 ★
1. s문자열을 **lower()** 을 이용하여 소문자로 바꿔준다.

2. **count()** 을 사용해서 p와 y의 개수를 세어준다.

3. 2개의 조건문을 만들어 p와 y의 개수를 비교해준다.
<br> &nbsp;&nbsp;&nbsp; ✔︎ 첫번째 조건문 : p와 y의 개수가 같다면 True로 반환하기
<br> &nbsp;&nbsp;&nbsp; ✔︎ 두번째 조건문 : p와 y의 개수가 다르다면 False로 반환하기