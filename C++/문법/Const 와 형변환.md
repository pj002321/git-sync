
더 이상 변할 필요가 없는 수, 또는 변해선 안되는 수를 정의할 때 쓰인다.

 ```cpp
const float PIE = 3.141592;
int r = 3;
float s = r*r*PIE;
```

# 데이터 형변환

특정 데이터형의 변수에 다른 데이터형의 값을 대입했을 때, 수식에 데이터형을 혼합하여 사용할 때 또는 함수에 매개변수를 전달할 때 쓰인다.

**C  : typeName(a) or (typeName)a** 
```c
int a = 3.141592;
=> a = 3

int a = float(3.141592);
or
int a = (float)3.141592;
=> a = 3.141592
```



```cpp
char c = 'M';
int a = static_cast<int> c;
=> a = 77;

```
**C++ : static_cast<typeName>





