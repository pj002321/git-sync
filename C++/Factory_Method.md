---
tags:
- C++
- DesignPatterns
- Factory
- OOP
- Architecture
aliases:
- FactoryMethod
- CppFactory
CMDS: "[[:books: 104 Terminologies]]" 
index: "[[:label: Research Notes]]"
author: "[[작성자]]" 
---

## 팩토리 메서드 (Factory Method)

#### What is Factory Method

- 정의 (Definition):
	- 팩토리 메서드는 객체 생성의 책임을 서브클래스에 위임하는 디자인 패턴입니다. (Gamma et al., 1994)
	- 구체적인 클래스의 인스턴스화를 캡슐화하고, 클라이언트 코드와 구체 클래스를 분리합니다.

- 예시 (Examples):
	- 기본 팩토리: `virtual Product* createProduct() = 0`
	- 템플릿 팩토리: `template<typename T> class Factory`
	- 정적 팩토리: `static std::unique_ptr<Product> create()`
	- 등록 가능한 팩토리: `static void registerCreator(const std::string& type, Creator creator)`
	- 추상 팩토리와의 조합: `class AbstractFactory { virtual Product* createProduct() = 0; }`

## Literature Review

#### Gamma et al., 1994
- [Design Patterns: Elements of Reusable Object-Oriented Software](https://www.amazon.com/Design-Patterns-Elements-Reusable-Object-Oriented/dp/0201633612)
	- Source: Addison-Wesley Professional
- 주요 내용 (Key points):
	- 팩토리 메서드는 객체 생성의 유연성을 제공합니다.
	- 의존성 역전 원칙을 따릅니다.
	- 확장에 열려있고 수정에 닫혀있는 구조를 만듭니다.

## 관련 개념 (Related Concepts)

- [[Abstract Factory (추상 팩토리)]] #cpp #design #patterns
	- 관련된 객체들의 생성을 추상화하는 패턴

- [[Dependency Inversion (의존성 역전)]] #cpp #design #principles
	- 팩토리 메서드가 따르는 설계 원칙

- [[Virtual Constructor (가상 생성자)]] #cpp #design #patterns
	- 팩토리 메서드의 대안이 되는 패턴 