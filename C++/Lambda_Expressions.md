
## 람다 표현식 (Lambda Expressions)

#### What is Lambda Expressions

- 정의 (Definition):
	- 람다 표현식은 C++11에서 도입된 익명 함수를 정의하는 방법입니다. (Stroustrup, 2013)
	- 함수 객체를 간단하게 생성할 수 있게 해주며, 현대적인 C++ 프로그래밍에서 널리 사용됩니다.

- 예시 (Examples):
	- 기본 람다: `[]() { return 42; }`
	- 캡처 절이 있는 람다: `[&x, y]() { return x + y; }`
	- 제네릭 람다: `[](auto x) { return x * x; }`
	- 반환 타입 지정: `[]() -> int { return 42; }`

## Literature Review

#### Stroustrup, 2013
- [The C++ Programming Language](https://www.stroustrup.com/4th.html)
	- Source: Addison-Wesley Professional
- 주요 내용 (Key points):
	- 람다는 지역 변수를 캡처할 수 있습니다.
	- STL 알고리즘과 함께 사용하기에 적합합니다.
	- 함수형 프로그래밍 스타일을 지원합니다.

## 관련 개념 (Related Concepts)

- [[Function Objects (함수 객체)]] #cpp #functor #object
	- 람다의 기반이 되는 개념

- [[STL Algorithms (STL 알고리즘)]] #cpp #stl #algorithms
	- 람다와 함께 자주 사용되는 알고리즘

- [[Modern C++ Features (모던 C++ 기능)]] #cpp #modern #features
	- C++11 이후 도입된 새로운 기능들 



[[C++]]  