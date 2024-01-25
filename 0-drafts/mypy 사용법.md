---
created-at: 2024-01-18T15:42
tags: 
description:
---
# Mypy 사용법

Mypy는 대표적인 파이썬 정적 타입 검사 도구이다.
파이썬의 타입 힌팅은 기본적으로 오류를 발생시키지 않기 때문에, mypy를 이용해 사전에 버그를 찾아낼 수도 있다.

1. mypy 설치
```bash
pip install mypy
```

2. mypy 실행
```bash
mypy main.py
```

3. 결과
- 정상
```bash
Success: no issues found in 1 source file
```

- 비정상
```bash
model.py:73: error: Incompatible types in assignment (expression has type "Tensor", variable has type "None")  [assignment]
agent.py:23: error: Incompatible types in assignment (expression has type "Tensor", variable has type "ndarray[Any, Any]")  [assignment]
Found 2 errors in 2 files (checked 1 source file)
```