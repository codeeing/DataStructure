# *Theme 1. 배열내의 데이터 추가하기*
```cpp
int num[10] = {1, 2, 3, 4, 5, 6, 7};
int count = 7;
```

<image src="https://github.com/codeeing/DataStructure/assets/135220759/e4b114f8-1680-4223-a9f5-1eb16d852e85" width="500"><br>
 위 그림과 같이 사이즈가 10인 배열이 있다. <br>배열 요소의 개수인 10개보다 초기화 데이터가 부족하므로, <br>남은 방은 0으로 초기화된 상태이다.

 > 만약 3번 방의 숫자 4를 삭제하려고 한다면, 어떻게 해야할까?

 ## 1. 전략
1. 하나씩 좌측으로 당겨온다. => for문으로 구현<br>
num[3] = num[4];<br>
num[4] = num[5];<br>
num[5] = num[6];<br><br>
2. 유효숫자의 개수를 하나 감소시킨다.<br>
--count;
 ## 2. 시각화
<image src="https://github.com/codeeing/DataStructure/assets/135220759/4e944a2e-5841-4c4c-aa47-61f1f73b2c1c" width="500"><br>
 ## 3. 코드화
 
 ```cpp
void deleteData(int *num, int *pcount, int index)
{
	int i;
	if (index < *pcount) {
        // 1. 유효숫자의 개수를 하나 감소시킨다.
		(*pcount)--;
        // 2. 하나씩 좌측으로 당겨온다.
		for (i = index; i < *pcount; i++) {
			num[i] = num[i + 1];
		}
	}
	else {
		return;
	}
}
```