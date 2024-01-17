---
created-at: 2024-01-17T21:29
tags: 
description:
---
# Linux shopt: not found 오류

wsl에서 pyenv를 설치하기 위해 .bashrc 파일을 수정 후 다음 명령어를 입력하니 'shopt: not found' 에러가 발생했다.

```bash
source ~/.bashrc
```

zsh를 쓰는 경우 위 명령어를 입력할 일이 있으면 다음과 같이 입력하면 된다.

```bash
exec bash
source ~/.bashrc
exec zsh
```