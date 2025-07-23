
공백없이 입력 받는 법
```cpp
char name[15];
cin>>name;
=> input : Jon Leo
=> output : Jon

cin.getline(name,15);
=> input : Jon Leo
=> output : Jon Leo

```


## String

C++ 에서 문자열을 다루는 방법 중 하나로, 배열 표기를 사용하여 string 객체에 저장되어있는 개별적인 문자들에 접근 할 수 있다.

배열은 다른 배열에 통째로 대입할 수 없다
=> string에서는 이것이 가능하다.

```cpp

char ch1[10];
char ch2[10]="JonLeo";
=> ch1 = ch2 (❌)

string s1;
string s2="JonLeo";

s1=s2;
=> Output s1 : JonLeo
=> Output s1[0] : J

```