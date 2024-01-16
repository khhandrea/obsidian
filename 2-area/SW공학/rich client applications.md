---
created-at: 2023-10-25T15:36
tags: 
description:
---
# Rich Client Applications
![[스크린샷 2023-11-08 오후 7.23.39.png]]
- Rich client UI는 좋은 인터넷에 연결 여부에 상관 없이 좋은 성능, 상호작용, 그리고 풍부한 UX를 제공한다.
- 혼자 동작하는 애플리케이션일 수도 있지만, 혼자 동작하며 다른 레이어의 사용자가 요구하는 동작과 소통하며 서비스를 제공하기도 한다.

## Key scenarios
- 비즈니스 레이어와 서비스 레이어를 총괄하는 얇은 애플리케이션부터, 대부분의 동작을 하되 외부의 정보와는 소통만 하는 애플리케이션까지 포함된다.
- 일부 애플리케이션은 자신만의 비즈니스 레이어와 데이터 레이어를 가지며 혼자서도 잘 작동한다.
- 다른 애플리케이션이 해당 애플리케이션을 사용하기 위해 비즈니스 혹은 데이터 레이어를 노출시키기도 한다.

## Key components
- UI components: 사용자가 애플리케이션과 상호작용할 수 있는 방법을 제공한다.
- User process components: 사용자와의 상호작용을 동기화하고 관장한다.
- Business components: 애플리케이션의 business logic을 구현한다.
- Business workflows: business process manage tools 등을 이용해 user process에 의해 데이터가 수집되면 실행할 여러 business logic들을 관장한다.
- Business entity workflows: 애플리케이션 내부에서 이동하는 데이터. 대부분 데이터 자료구조.
- Application façade (optional): 여러 business operation을 하나의 message-based operation으로 변경한다.
- Data access logic components: 데이터 액세스에 필요한 logic을 구현해 데이터 접근의 기능성과 유지성을 높인다.
- Data helpers: 
- Service agents: 외부의 정보와 소통