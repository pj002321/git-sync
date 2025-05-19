
## 팩토리 메서드 패턴 (Factory Method Pattern)

#### What is Factory Method Pattern

- 정의 (Definition):
    - 팩토리 메서드는 **객체 생성 코드를 서브클래스에 위임**하여, 객체 생성 구조를 유연하게 만드는 생성(Creational) 디자인 패턴입니다.
    - 객체 생성의 책임을 분리해 확장성과 유지보수성을 높입니다.

- 예시 (Examples):
    - 게임에서 무기/몬스터/아이템 등 다양한 객체 생성
    - 코드 예시 (C++):
```cpp
class Product {
public:
    virtual void Use() = 0;
    virtual ~Product() = default;
};
class ConcreteProduct : public Product {
public:
    void Use() override { /* ... */ }
};
class Creator {
public:
    virtual std::unique_ptr<Product> Create() = 0;
};
class ConcreteCreator : public Creator {
public:
    std::unique_ptr<Product> Create() override {
        return std::make_unique<ConcreteProduct>();
    }
};
```

## Literature Review

#### Gamma et al., 1994
- [Design Patterns: Elements of Reusable Object-Oriented Software](https://en.wikipedia.org/wiki/Factory_method_pattern)
    - 팩토리 메서드의 구조, 장단점, 활용 사례

## 주제별 세부 내용 정리와 설명
- **구조**: Creator(생성자)와 Product(생성 객체)로 분리, 서브클래스가 객체 생성 책임
- **Modern C++**: 스마트 포인터(std::unique_ptr 등)로 메모리 관리
- **장점**: 객체 생성 구조 분리, 확장성/유지보수성 향상
- **단점**: 클래스 수 증가, 구조 복잡도 증가
- **게임/엔진 활용**: 다양한 무기/몬스터/아이템/이펙트 등 동적 생성에 활용
- **실전 팁**: 스마트 포인터/RAII로 메모리 관리, DI/확장성 고려

## 예상 면접 질문과 답변
- Q. 팩토리 메서드 패턴이란?
  A. 객체 생성 코드를 서브클래스에 위임해 유연하게 만드는 패턴입니다.
- Q. Modern C++에서 팩토리 메서드 구현 시 주의점은?
  A. 스마트 포인터로 메모리 관리, 확장성 고려.

## 관련 개념 (Related Concepts)
- [[디자인 패턴 (Design Pattern)]] #designpattern #cpp
- [[추상 팩토리 패턴]] #abstractfactory #pattern

## 관련 개념 (Related Concepts)

	- 관련된 객체들의 생성을 추상화하는 패턴

	- 팩토리 메서드가 따르는 설계 원칙

	- 팩토리 메서드의 대안이 되는 패턴 



[[C++]]  