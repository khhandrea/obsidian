---
created-at: 2023-10-26T03:17
tags: 
description:
---
# Object-Oriented Design
- System behavior description by system interaction diagram

1. 시스템의 Use-case로부터 system sequence diagram을 만든다.
2. System sequence diagram
3. System operations
4. Contracts
5. Collaboration diagram
6. Class diagram

- c.f. conceptual diagram


- System sequence diagram: actors와 systems 사이의 events를 표현
- System behavior: 시스템이 하는 일을 방법을 제외하고 설명
- System interaction diagrams: use-case의 일부를 보여주는 특정한 시나리오
- Use-case evens의 과정을 위해 system interaction diagram이 완성되어야 한다.

## Contracts
- Contracts: operation이 어떤 산출물을 내는지를 서술
	- 어떻게 수행될 지보다 어떤 일이 일어날지를 강조한다.
- System operation contracts: 시스템 operation에 대하여 시스템 전반에 어떤 일이 일어나는지를 서술한다.

- 구성 요소
	- Name
	- Responsibilities
	- Type
	- Cross references
	- Exceptions
	- Output
	- Pre-conditions
	- Post-conditions