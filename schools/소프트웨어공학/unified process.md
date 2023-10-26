---
created-at: 2023-10-24T18:11
tags: 
description:
---
# Unified Process
## 4 phases in UP
- Inception phase
	- 현행 비즈니스 프로세스의 문제점 분석
	- Stakeholder가 기술한 비전을 만족하기 위해 시스템의 요구사항 식별 및 범위 등을 결정
	- 주요 항목
		- [[business modeling|Business ]]
		- [[requirements capture|Requirements capture]]
		- UI prototyping
		- Feasibility prototyping[^1]
- Elaboration phase
	- 요구사항 만족을 위해 시스템을 분석하고 설계
	- Baseline architecture를 작성
	- 주요 항목
		- Analysis
		- [[SA design|Design]]
		- Implementation
- Construction phase
	- SW 아키텍처에 따라 설계된 컴포넌트들을 구현하고 테스트
	- 실행 가능한 시스템을 만들어 내는 단계
- Transition phase
	- 제품을 사용자에게 인도하는 단계

## 4 milestones in phases
- Inception phase: vision & scope
- Elaboration phase: baseline architecture
- Construction phase: initial capability
- Transition phase: product release

## 9 disciplnes in UP
1. Business modeling
2. [[requirements capture|Requirements capture]]
3. [[OOA|Analysis]] & [[SA design|design]]
4. Implementation
5. Test
6. Deployment
7. Configuration & change management
8. Project management
9. Environment

## 주요 UP disciplines
- Business modeling: 요구사항을 이해하고 비즈니스 프로세스 모델과 비즈니스 도메인을 만든다.
- Requirements capture: 시스템의 기능적 요구 사항이나 비기능적 요구 사항을 분석한다.
- Analysis: 중요 유즈케이스에 대해 분석 클래스를 식별하고 상호 작용 모델을 작성한다.
- Design: 요구 사항을 만족시키는 SW 아키텍처를 설계하고, 각 주요 모듈에 대해 설계한다.
- Implementation: 아키텍처 상의 주요 모듈들을 특정 언어나 플랫폼에 맞도록 구현한다.
- Test: 구현된 모듈에 대한 단위 테스팅이나 통합 테스트를 수행한다.

## 4 characteristics in UP
- Use-case-driven
	- [[use-case diagram|Use-case]]는 FR을 포함하고 있기 때문에, 모든 phases와 [[architecture views|views]]에 영향을 미치게 된다.
- Architecture-centric
	- 모든 모델은 baseline architecture를 기반으로 만든다.
	- Baseline architecture: elaboration phase에 만들어지는 skeleton system (executable code)
	- Baseline architecture가 최종 코드의 10퍼센트정도만 포함되더라도, 
	- 전체 산출물은 elaboration phase 이후 실제 기능들이 채워지고, 아키텍처 기술서는 elaboration phase 이후 작성 수준이 견고해진다.
- Controlled iterative model
	- 매 phase에 iteration이 존재한다.
- Incremental build model
	- 각 제품이 전보다 좋은 기능성을 가지고 있다.
	- 디자인이 잘 적용되었는지확인하는 기회를 가진다.
	- 팀별로 스케줄을 맞추는 데에 도움이 된다.