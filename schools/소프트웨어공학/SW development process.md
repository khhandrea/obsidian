---
created-at: 2023-10-26T01:22
tags: 
description:
---
# SW Development Process
```mermaid
flowchart TD

1["Business Modeling"]
2["Technical Feasibility Test"]
3["Functional Requirements"]
4["Quality Requirements"]
5["Problem Analysis"]
6["Solution Design"]
7["Implementation"]
8["Integration"]
9["Testing"]
10["Transition"]

1 --> 2
2 --> 3
subgraph Requirement Capture
	3 --> 4
end
4 --> 5
subgraph Architecture Modeling
	5 --> 6
end
6 --> 7
7 --> 8
8 --> 9
9 --> 10
```

OO SW development process
```mermaid
flowchart TD

1["Define use cases"]
2["Define conceptual model"]
3["Define collaboration diagrams"]
4["Define design class diagrams"]

1 --> 2 --> 3 --> 4
```

## SW modeling & diagrams
| Step                           | Diagrams                                            | [[architecture views\|Architecture views]]                     |
| ------------------------------ | --------------------------------------------------- | --------------------------- |
| Business Modeling              | [[activity diagram\|Activity]]/[[info flow diagram\|Info Flow]] Diagram                          | Use-case view               |
| Requirements Capture           | [[use-case diagram\|Use-case Diagram]]                                    | Use-case view               |
| Problem Analysis               | [[class diagram\|Conceptual Model in Class Diagram]]                   | Logical & process view      |
| Logical Solution Design        | [[collaboration diagram\|Collaboration]]/[[sequence diagram\|Sequence]] Diagram, Class/State Diagram | Logical & process view      |
| Physical Implementation Design | [[component diagram\|Component]]/[[package diagram\|Package]]/[[model diagram\|Model]] Diagram, [[deployment diagram\|Deployment Diagram]] | Development & physical view |
