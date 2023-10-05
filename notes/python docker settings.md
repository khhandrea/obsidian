---
created-at: 2023-09-26T12:48
tags:
  - note
description: Docker 세팅 생각해보기
---
# Python Docker settings
## Todo
	- jupyter notebook 연결하는 법
	- tensorboard 연결하는 법

## Note
그냥
- Volume으로 로컬 디렉토리와 연결
- Jupyter 환경 만든 후 jupyter notebook과 연결
- pip install로 requirements의 라이브러리들을 설치
- 각 개발 환경을 image로 만드는거임
- 코드는 github에 올리는거임
- 만든 image는 특별하지 않는 이상 hub에 올릴 필요는 없긴 함

필요할 이미지
- vanilla python image
- requirements python image
- jupyter notebook python image
- git 상태 알려주는?

1. vanilla python container에서 코드를 작성한다.
2. `pip freeze > requirements.txt` 로 라이브러리를 작성한다.
3. requirements를 기반으로 새 python image를 (다시) 만든다.
4. 새 image를 열어 코딩을 한다.

## References
- [[docker 기초] 도커 nvidia gpu 초기 세팅 방법 (tistory.com)](https://yeko90.tistory.com/entry/docker-nvidia-gpu-setting)
- [Docker로 개발환경을 만들어보자 - Seorenn Note](https://seorenn.github.io/note/docker-development-environment.html)
- 