# *Theme 1. 배열내의 데이터 추가하기*
```cpp
int num[10] = {1, 2, 3, 4, 5, 6, 7};
int count = 7;
```

<image src="https://github.com/codeeing/DataStructure/assets/135220759/a19bbfe0-ba12-46cb-8c10-c4678ab185e4" width="500"><br>
 위 그림과 같이 사이즈가 10인 배열이 있다. <br>배열 요소의 개수인 10개보다 초기화 데이터가 부족하므로, <br>남은 방은 0으로 초기화된 상태이다.

 > 만약 4번 방에 숫자 8을 삽입하려고 한다면, 어떻게 해야할까?

 ## 1. 전략
1. 우측으로 민다. => for문으로 구현<br>
num[7] = num[6];<br>
num[6] = num[5];<br>
num[5] = num[4];<br><br>
2. 4번 방에 숫자 8을 삽입한다.<br>
num[4] = 8;<br><br>
3. 유효숫자의 개수를 하나 증가시킨다.<br>
++count;
 ## 2. 시각화
<image src="https://github.com/codeeing/DataStructure/assets/135220759/50c71a0f-82c4-420c-a41e-a86171a4b384" width="500"><br>
 ## 3. 코드화
 
 ```cpp
void insertData(int *np, int *pcount, int index, int data){
    int i;
	if (index <= *pcount) {
        // 1. 우측으로 민다.
		for (i = *pcount; i > index; i--) {
			np[i] = np[i - 1];
		}
        // 2. 4번 방에 숫자 8을 삽입한다.
		np[index] = data;
        // 3. 유효숫자의 개수를 하나 증가시킨다.
		(*pcount)++;
	}
	else {
		return;
	}
}
```