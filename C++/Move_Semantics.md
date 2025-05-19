
## 이동 의미론 (Move Semantics)

#### What is Move Semantics

- 정의 (Definition):
	- 이동 의미론은 C++11에서 도입된 기능으로, 객체의 리소스를 다른 객체로 이동시키는 메커니즘입니다. (Stroustrup, 2013)
	- 불필요한 복사를 피하고 성능을 향상시키는 데 사용됩니다.

- 예시 (Examples):
	- 이동 생성자: `MyClass(MyClass&& other)`
	- 이동 할당 연산자: `MyClass& operator=(MyClass&& other)`
	- std::move: `std::move(obj)`
	- std::forward: `std::forward<T>(arg)`

## Literature Review

#### Stroustrup, 2013
- [The C++ Programming Language](https://www.stroustrup.com/4th.html)
	- Source: Addison-Wesley Professional
- 주요 내용 (Key points):
	- 이동 후 원본 객체는 유효하지만 상태는 지정되지 않습니다.
	- 이동 연산은 복사보다 효율적입니다.
	- rvalue 참조를 통해 이동 가능한 객체를 식별합니다.

## 관련 개념 (Related Concepts)

	- 이동 의미론의 기반이 되는 참조 타입
	- 인자의 값을 보존하면서 전달하는 기법
	- C++11 이후 도입된 새로운 기능들 

[[C++]]  