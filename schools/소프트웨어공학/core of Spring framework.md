---
created-at: 2023-10-25T15:36
tags: 
description:
---
# Core of Spring Framework
- [[SOLID#SOLID OO design principles#DIP(Dependency Inversion Principle)|DI(Dependency Injection)]] Container를 가진다.

- 일반적인 애플리케이션에서의 의존 관계
```mermaid
flowchart TD

A["인스턴스A"]
B["인스턴스B"]

A --"생성한 후 사용"--> B
```

- DI container를 활용한 인스턴스 생성
```mermaid
flowchart TD

A["인스턴스A"]
B["인스턴스B"]
Interface["인터페이스"]
Container["DI 컨테이너"]

A --"인스턴스B 취득"--> Container
Container --"생성"--> B
A --"사용"--> Interface --> B
```

- DI container를 활용한 의존성 주입
```mermaid
flowchart TD

A["인스턴스A"]
B["인스턴스B"]
C["인스턴스C"]
Interface1["인터페이스1"]
Interface2["인터페이스2"]
Container["DI 컨테이너"]

Container --> A
C --"인스턴스 A 취득"--> Container
C --"사용"--> Interface1 --> A
Container --"생성"--> B

subgraph "컴포넌트"
	A --"사용"--> Interface2 --> B
	B --"주입"--> A
end
```
