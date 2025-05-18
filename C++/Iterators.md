
## 반복자 (Iterators)

#### What is Iterators

- 정의 (Definition):
	- 반복자는 STL 컨테이너의 요소에 접근하는 방법을 제공하는 객체입니다. (Stroustrup, 2013)
	- 포인터와 유사한 인터페이스를 제공하며, 컨테이너의 내부 구현을 추상화합니다.

- 예시 (Examples):
	- 입력 반복자: `istream_iterator`
	- 출력 반복자: `ostream_iterator`
	- 순방향 반복자: `forward_list::iterator`
	- 양방향 반복자: `list::iterator`
	- 임의 접근 반복자: `vector::iterator`

## Literature Review

#### Stroustrup, 2013
- [The C++ Programming Language](https://www.stroustrup.com/4th.html)
	- Source: Addison-Wesley Professional
- 주요 내용 (Key points):
	- 반복자는 컨테이너와 알고리즘을 분리합니다.
	- 다양한 반복자 카테고리가 존재합니다.
	- 반복자 무효화에 주의해야 합니다.

## 관련 개념 (Related Concepts)

- [[STL Containers (STL 컨테이너)]] #cpp #stl #containers
	- 반복자가 접근하는 데이터 구조

- [[STL Algorithms (STL 알고리즘)]] #cpp #stl #algorithms
	- 반복자를 사용하는 알고리즘

- [[Iterator Invalidation (반복자 무효화)]] #cpp #iterator #safety
	- 반복자가 유효하지 않게 되는 상황 


[[C++]]  