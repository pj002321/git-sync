
## 싱글톤 패턴 (Singleton Pattern)

#### What is Singleton Pattern

- 정의 (Definition):
	- 싱글톤은 **프로그램 전체에서 단 하나의 인스턴스**만 존재하도록 보장하는 생성(Creational) 디자인 패턴입니다.
	- 전역 상태, 리소스 관리, 매니저 등에 활용됩니다.

- 예시 (Examples):
	- 게임 엔진의 ResourceManager, Logger 등
	- 코드 예시 (C++11 이상, 스레드 안전):
```cpp
class GameManager {
public:
	static GameManager& Instance() {
		static GameManager instance;
		return instance;
	}
	GameManager(const GameManager&) = delete;
	void operator=(const GameManager&) = delete;
private:
	GameManager() {}
};
```

## 주제별 세부 내용 정리와 설명
- **구조**: 생성자 private, static 인스턴스, 복사/대입 금지
- **Modern C++**: C++11 static 지역 변수로 스레드 안전 보장
- **장점**: 전역 인스턴스 보장, 리소스 공유, 접근 용이
- **단점**: 테스트/확장 어려움, 의존성 증가, 멀티스레드 환경 주의(구버전)
- **게임/엔진 활용**: 리소스, 설정, 로깅 등 전역 관리에 사용
- **실전 팁**: 남용 금지, DI/테스트 고려, Modern C++에서 static 지역 변수 활용

## 예상 면접 질문과 답변
- Q. 싱글톤 패턴이란?
	A. 프로그램 전체에서 단 하나의 인스턴스만 존재하도록 보장하는 패턴입니다.
- Q. Modern C++에서 싱글톤을 안전하게 구현하는 방법은?
	A. static 지역 변수(C++11 이상)로 스레드 안전 보장.
- Q. 싱글톤의 단점은?
	A. 테스트/확장 어려움, 의존성 증가.

## 관련 개념 (Related Concepts)
- [[디자인 패턴 (Design Pattern)]] #designpattern #cpp
- [[전역 객체]] #global #object 


[[C++]]  