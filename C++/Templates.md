
## 템플릿 (Templates)

#### What is Templates

- 정의 (Definition):
	- 템플릿은 타입이나 값에 대해 매개변수화된 C++의 기능입니다. (Stroustrup, 2013)
	- 컴파일 시점에 코드를 생성하며, 타입 안전성을 보장합니다.

- 예시 (Examples):
	- 함수 템플릿: `template<typename T> T max(T a, T b)`
	- 클래스 템플릿: `template<typename T> class Vector`
	- 변수 템플릿: `template<typename T> constexpr T pi = T(3.14159265359)`
	- 별칭 템플릿: `template<typename T> using Vec = std::vector<T>`
	- 개념(Concepts): `template<typename T> requires std::integral<T>`

## Literature Review

#### Stroustrup, 2013
- [The C++ Programming Language](https://www.stroustrup.com/4th.html)
	- Source: Addison-Wesley Professional
- 주요 내용 (Key points):
	- 템플릿은 컴파일 시점 다형성을 제공합니다.
	- SFINAE와 템플릿 메타프로그래밍이 가능합니다.
	- C++20의 Concepts로 템플릿 사용이 더 쉬워졌습니다.

## 관련 개념 (Related Concepts)

	- 템플릿 오버로딩의 핵심 메커니즘

	- 템플릿 매개변수에 대한 제약 조건

	- 컴파일 시점에 수행되는 프로그래밍 


[[C++]]  