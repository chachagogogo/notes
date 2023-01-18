인자로 `주소`를 전달해야 한다.
`값`을 전달하면 안된다.

```c
int main()
{
	int num;
	scanf("%d", &num); // 입력값을 "num의 주소"에 할당

	char str[];
	printf("%s", str); // str 자체가 포인터 상수이므로 & 연산자를 붙이면 안된다
    
    return 0;
}
```