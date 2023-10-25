---
created-at: 2023-10-25T15:23
tags: 
description:
---
# GRASP Design Principles
- General Responsibility Assignment Software Patterns
- Fundamental하고 universal한 SW를 위한 OO design principles

- 클래스들과 그 클래스들 에 책임을 부여하는 방법을 제시한다.

1. Low coupling
2. High cohesion
3. Expert
4. Creator
5. Controller
6. Don't talk to stranger

## Low coupling
의존성을 낮추고 재사용성을 높이기 위해 coupling을 낮게 유지해야 한다.
- Coupling(결합도): 한 클래스가 다른 클래스에 연결되거나 관여하는 정도
- High coupling의 문제점
	- 한 클래스의 변화가 연관된 클래스들의 변화를 강요한다.
	- 이해하기 어렵다.
	- 재사용하기 어렵다.

## High cohesion
관리할 수 있을만한 복잡성을 유지하기 위해 cohesion을 높에 유지하도록 책임을 부여해야 한다.
- Cohesion(응집도): 한 클래스의 책임들이 연관되거나 집중되어 있는 정도
- Low cohesion의 문제점
	- 한 클래스가 서로 관련 없는 일을 하거나 너무 많은 일을 하게 된다.
	- 변화에 빈번히 강요된다.
	- 이해하기 어렵다.
	- 재사용하기 어렵다.

## Expert
정보를 가지고 있는 전문가(information expert)에게 책임을 부여해야 한다.
- 장점
	- [[OOP#Object-Oriented Programming#4 Pillars of OOP|Encapsulation]]을 유지할 수 있다.
	- Low coupling을 유지할 수 있다.
	- 클래스가 가진 정보에 따라 행동(behavior)가 분배될 수 있다.

## Creator
다음 조건에 맞는 클래스 A의 인스턴스를 만들 때에는 책임을 가진 클래스 B를 사용해야 한다.
- B가 A를 종합한다.
- B가 A를 포함한다.
- B가 A를 추적한다.
- B가 A를 밀접하게 사용한다.
- B가 A를 생성할 때 필요한 데이터를 가지고 있다.

## Controller
외부 event와 event handler를 연결하는 다음과 같은 조건에서, event를 받아 event handler에게 event를 전달하는 오브젝트(=controller)를 사용해 간접 coupling을 만들어야 한다.
- 전반적인 시스템이나 비즈니스, 기관을 표현한다. (Façade controller, 퍼사드 컨트롤러)
- 실제 세계의 활성화된 개념을 표현한다. (role controller)
- Use-case의 모든 event를 다루는 artificial handler를 표현한다. (use-case controller)
	- Eg. \<UseCaseName\> handler

## Don't talk to strangers
Coupling을 낮추기 위해, 서로 연관이 없는 두 클래스는 직접적으로 상호작용하지 말아야 한다. 대신, 다른 클래스를 통해 간접적으로 사용하는 방법이 있다.