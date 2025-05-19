
## 자원 획득 초기화 (RAII)

#### What is RAII

- 정의 (Definition):
	- RAII(Resource Acquisition Is Initialization)는 리소스의 수명을 객체의 수명에 바인딩하는 C++ 프로그래밍 기법입니다. (Stroustrup, 2013)
	- 리소스 획득은 객체 생성 시점에, 해제는 객체 소멸 시점에 자동으로 이루어집니다.

- 예시 (Examples):
	- 스마트 포인터: 메모리 자동 관리
	- 파일 스트림: 파일 자동 닫기
	- 락 가드: 뮤텍스 자동 해제

## Literature Review

#### Stroustrup, 2013
- [The C++ Programming Language](https://www.stroustrup.com/4th.html)
	- Source: Addison-Wesley Professional
- 주요 내용 (Key points):
	- 예외 안전성을 보장합니다.
	- 리소스 누수를 방지합니다.
	- 코드의 가독성과 유지보수성을 높입니다.

## 관련 개념 (Related Concepts)

	- RAII 패턴을 사용한 메모리 관리

	- 예외 발생 시에도 리소스가 안전하게 관리됨

	- RAII의 핵심이 되는 객체 소멸 시점 처리 



[[C++]]  