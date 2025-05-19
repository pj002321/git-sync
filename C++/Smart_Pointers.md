
## 스마트 포인터 (Smart Pointers)

#### What is Smart Pointers

- 정의 (Definition):
	- 스마트 포인터는 동적 메모리 관리를 자동화하는 포인터 클래스입니다. (Stroustrup, 2013)
	- C++11부터 도입된 기능으로, 메모리 누수를 방지하고 예외 안전성을 보장합니다.

- 예시 (Examples):
	- unique_ptr: 소유권이 단독으로 있는 스마트 포인터
	- shared_ptr: 참조 카운팅을 사용하는 공유 스마트 포인터
	- weak_ptr: shared_ptr의 순환 참조를 방지하는 약한 참조 포인터

## Literature Review

#### Stroustrup, 2013
- [The C++ Programming Language](https://www.stroustrup.com/4th.html)
	- Source: Addison-Wesley Professional
- 주요 내용 (Key points):
	- unique_ptr은 이동만 가능하고 복사는 불가능합니다.
	- shared_ptr은 참조 카운팅을 통해 메모리를 자동으로 관리합니다.
	- weak_ptr은 shared_ptr의 순환 참조 문제를 해결합니다.

## 관련 개념 (Related Concepts)

	- 스마트 포인터가 해결하는 메모리 관리 문제

	- 스마트 포인터의 기본이 되는 디자인 패턴

	- C++11 이후 도입된 새로운 기능들 