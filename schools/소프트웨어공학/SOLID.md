---
created-at: 2023-10-25T15:22
tags: 
description:
---
# SOLID OO design principles
Understandable, flexible, maintainable한 프로그램을 위한 Object oriented design 원칙
1. SRP(Single Reponsibility Principle)
2. OCP(Open Closed Principle)
3. LSP(Liskov Substituion Principle)
4. ISP(Interface Segregation Principle)
5. DIP(Dependency Inversion Principle)

- 2, 3, 4, 5는 좋은 interface에 대한 원칙이다.


## SRP(Single Responsibility Principle)
- Method나 class를 변경할 이유는 오직 하나여야 한다. (A method or class must have one reason to change)
- Method나 class는 오직 하나의 책임을 가져야 한다.

## OCP(Open Closed Principle)
- Method나 class는 확장에는  열려 있고 수정에는 닫혀 있어야 한다.
	- Interface에 대한 지침

## LSP(Liskov Substitution Principle)
- 한 클래스의 인스턴스는 그것의 하위 클래스로 대체될 수 있어야 한다.

## ISP(Institution Segregation Principle)
- 클래스는 사용자 친화적인 인터페이스(client-specific interface)를 가져야 한다.
- 사용자는 사용하지 않는 기능에 대해 강요되어선 안 된다. (-> interface를 잘게 나눠야 한다.)

## DIP(Dependency Inversion Principle)
- 상위 모듈은 하위 모듈에 의존해서는 안 된다.
	-> 상위 모듈과 하위 모듈은 모두 추상화에 의존해야 한다.
- 추상화는 세부 구현에 의존해서는 안 된다.
	-> 세부 구현이 추상화에 의존해야 한다.

- 예시: [[core of Spring framework|Spring framework]]