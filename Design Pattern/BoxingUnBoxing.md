---
tags:
- boxing-unboxing-csharp
- dotnet-performance
- 게임개발-면접-타입변환-성능
aliases:
- Boxing
- UnBoxing
- 박싱
- 언박싱

## 박싱과 언박싱 (Boxing & Unboxing)

#### What is Boxing & Unboxing

- 정의 (Definition):
    - 박싱(Boxing)은 값 타입(Value Type, 예: int, float 등)을 참조 타입(object)으로 변환하는 과정입니다.
    - 언박싱(Unboxing)은 참조 타입에서 다시 값 타입으로 변환하는 과정입니다.
    - C#/.NET에서 타입 변환, 컬렉션, 인터페이스 사용 시 자주 발생합니다.

- 예시 (Examples):
    - int → object (박싱), object → int (언박싱)
    - 코드 예시 (C#):
```csharp
int n = 10;
object obj = n; // 박싱
int m = (int)obj; // 언박싱
```

## Literature Review

#### Microsoft Docs
- [Boxing and Unboxing (C# Programming Guide)](https://learn.microsoft.com/en-us/dotnet/csharp/programming-guide/types/boxing-and-unboxing)
    - 박싱/언박싱의 원리, 성능 영향, 주의점

## 주제별 세부 내용 정리와 설명
- **구조**: 값 타입 → 힙에 object로 복사(박싱), object → 값 타입으로 변환(언박싱)
- **장점**: 값 타입을 참조 타입처럼 다룰 수 있음, 컬렉션/인터페이스 활용
- **단점**: 성능 저하(GC/힙 할당), 불필요한 변환 주의
- **C#/.NET/Unity 실전**: 컬렉션(List<object> 등), 인터페이스, 박싱 최소화로 성능 최적화
- **실전 팁**: 제네릭 사용, 박싱/언박싱 최소화, 프로파일링으로 성능 확인

## 예상 면접 질문과 답변
- Q. 박싱과 언박싱이란?
  A. 값 타입을 참조 타입(object)으로 변환(박싱), 다시 값 타입으로 변환(언박싱)하는 과정입니다.
- Q. 박싱/언박싱의 단점은?
  A. 성능 저하, GC/힙 할당 증가.
- Q. 박싱/언박싱을 줄이는 방법은?
  A. 제네릭, 구조체, 인터페이스 최적화 등 활용.
- Q. Unity에서 박싱/언박싱이 성능에 미치는 영향은?
  A. GC/프레임 드랍 유발, 최적화 필요.

## 관련 개념 (Related Concepts)
- [[C# 타입 시스템]] #csharp #type #system
- [[성능 최적화]] #performance #optimization 