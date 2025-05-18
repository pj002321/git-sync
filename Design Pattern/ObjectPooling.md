---
tags:
- object-pooling-pattern-design
- optimization-game
- 게임개발-면접-최적화-재사용
aliases:
- ObjectPooling
- 오브젝트풀링

## 오브젝트 풀링 패턴 (Object Pooling Pattern)

#### What is Object Pooling Pattern

- 정의 (Definition):
    - 오브젝트 풀링은 **반복적으로 생성/파괴되는 객체**를 미리 생성해두고 재사용하는 최적화 패턴입니다.
    - 게임에서 총알, 이펙트 등 잦은 생성/파괴가 필요한 경우 성능 향상에 필수적입니다.

- 예시 (Examples):
    - 총알, 파티클, 이펙트 등 반복 사용 오브젝트
    - 코드 예시 (C#):
```csharp
public class ObjectPool<T> where T : new() {
    private readonly Queue<T> pool = new();
    public T Get() => pool.Count > 0 ? pool.Dequeue() : new T();
    public void Release(T obj) => pool.Enqueue(obj);
}
```

## Literature Review

#### Gamma et al., 1994
- [Design Patterns: Elements of Reusable Object-Oriented Software](https://en.wikipedia.org/wiki/Object_pool_pattern)
    - 오브젝트 풀의 구조, 장단점, 활용 사례

## 주제별 세부 내용 정리와 설명
- **구조**: 미리 객체를 생성, 필요 시 꺼내 쓰고 반환
- **장점**: 성능 향상, GC/메모리 할당 최소화, 실시간 게임에 적합
- **단점**: 메모리 선점, 풀 크기 관리 필요, 복잡도 증가
- **Unity/게임 개발**: 총알, 이펙트, 적 등 반복 생성/파괴 오브젝트에 필수
- **실전 팁**: 풀 크기 조절, 동적 확장/축소, 반환 시 초기화 주의

## 예상 면접 질문과 답변
- Q. 오브젝트 풀링 패턴이란?
  A. 반복적으로 생성/파괴되는 객체를 미리 만들어 재사용하는 최적화 패턴입니다.
- Q. 오브젝트 풀링의 장단점은?
  A. 성능 향상/GC 최소화(장점), 메모리 선점/풀 관리(단점).
- Q. Unity에서 오브젝트 풀링 활용 예시는?
  A. 총알, 이펙트, 적 등 반복 생성/파괴 오브젝트.
- Q. 오브젝트 풀링 구현 시 주의점은?
  A. 반환 시 상태 초기화, 풀 크기 관리.

## 관련 개념 (Related Concepts)
- [[디자인 패턴 (Design Pattern)]] #designpattern #oop
- [[최적화 패턴]] #optimization #pattern 