## ⌜문제 설명⌟
### 배열 array의 i번째 숫자부터 j번째 숫자까지 자르고 정렬했을 때, k번째에 있는 수를 구하는 문제입니다.

#### 예를 들어 array가 [1, 5, 2, 6, 3, 7, 4], i = 2, j = 5, k = 3이라면

1. array의 2번째부터 5번째까지 자르면 [5, 2, 6, 3]입니다.
2. 1에서 나온 배열을 정렬하면 [2, 3, 5, 6]입니다.
3. 2에서 나온 배열의 3번째 숫자는 5입니다.
#### 배열 array와 [i, j, k]를 원소로 가진 2차원 배열 commands가 매개변수로 주어질 때, commands의 모든 원소에 대해 앞서 설명한 연산을 적용했을 때 나온 결과를 배열에 담아 반환하는 solution 함수를 작성해주세요.

```python
def solution(array, commands):
    result_list = []
    for list in commands:                #먼저 for문을 이용해서 commands 안에 있는 리스트부터 쪼개버리기
        i = list[0]                      #i, j , k 설정
        j = list[1]
        k = list[2]
        
        slicing = array[i -1 : j]        #i번쨰부터 j번째까지 슬라이싱을 하자..
        sorted_slicing = sorted(slicing) #그런데 정렬해야하네 ㅋㅋ
        result = sorted_slicing[k-1]     #슬라이싱을 한 것에 k번째 숫자를 뽑아내자..
        
        result_list.append(result)       #빈 리스트에 추가해주기
    return result_list

array = [1, 5, 2, 6, 3, 7, 4]
commands = [[2, 5, 3], [4, 4, 1], [1, 7, 3]]

print(solution(array, commands))
```

## ☻ 내가 몰랐던 것들 ☺︎
* 처음에 코드 이해를 잘 못해가지고, 집중하면서 문제를 풀지 못함

## ☆ 문제 접근 방식 ★
1. for문을 이용해서 commands의 이차원 리스트를 풀어주어야겠다고 생각했음.

2. commands의 0번째 인덱스(i)와 1번째 인덱스(j)는 i번째부터 j번째까지 잘라주는 걸 의미하고, 2번째 인덱스(k)는 k번째 숫자를 고르는 걸 의미하기 때문에, i, j, k에 인덱스를 할당해줌.

3. 슬라이싱을 이용해서 i번째부터 j번째까지 뽑아내자고 생각함.
<br> &nbsp;&nbsp;&nbsp; ✔︎ 여기서 i-1을 해주어야 함. (왜냐하면 2번째는 array에서 1번째 인덱스이기 때문이다.)

4. 자른 순서를 배열해주어야 하기 때문에 sort()를 이용했음.

5. 마지막으로 k번째 숫자를 뽑아줘야 하기 때문에 3번과 동일하게 k-1을 이용해 해당 리스트의 인덱스를 뽑아줌.

6. 만들어 놓은 빈 리스트를 5번의 결과값을 추가시키면 끝임. 