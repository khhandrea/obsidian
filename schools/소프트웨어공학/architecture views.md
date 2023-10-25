---
created-at: 2023-10-24T17:50
tags: 
description:
---
# Architecture Views
## 4+1 views
- Conceptual view
	1. Logical view: end users를 위한 functionality 중심
	2. Process view: system integrators를 위한 performance 중심
- Physical view
	3. Implementation view: programmers를 위한 configuration management 중심
	4. Deployment view: system engineers를 위한 system topology 중심
- Use-case view

### Use-case view
- Use-case diagram
### Logical view
- [[collaboration diagram|Collaboration diagram]]
- [[sequence diagram|Sequence diagram]]
- [[class diagram#Class Diagram#Domain model class diagram|Domain model class diagram]]
- [[class diagram#Class Diagram#Implementation model class diagram]]
- [[state machine diagram|State machine diagram]]
### Process view
- Process flow diagram
### Implementation view
- [[component diagram|Component diagram]]
- [[package diagram|Package diagram]]
- [[model diagram|Model diagram]]
### Deployment view
- [[deployment diagram|Deployment diagram]]
## Architecture views in UML
### 1. Business modeling
- Activity/info flow diagram
### 2. Requirement capture
- Use-case diagram
### 3. Problem analysis
- Conceptual model in class diagram
### 4. Logical solution design
- Collaboration/sequence diagram
- Class diagram
- State diagram
### 5. Physical implementation design
- Component/package/model diagram
- Deployment diagram

## 정적 모델 vs. 동적 모델
- 정적 모델(구조적 다이어그램)
	- Class diagram
	- Component diagram
	- Package diagram
	- Deployment diagram
- 동적 모델(행동 다이어그램)
	- Use-case diagram
	- Activity diagram
	- Sequence diagram
	- Collaboration diagram