---
created-at: 2024-01-17T21:18
tags: 
description:
---
# Linux pyenv 설치

wsl 기반의 linux로 pipenv가 설정된 프로젝트를 실행하려고 명령어를 입력했더니 다음과 같은 오류가 떴다.
```bash
pipenv install
```

> Warning: Python 3.11.6 was not found on your system...
> Neither 'pyenv' nor 'asdf' could be found to install Python.
> You can specify specific versions of Python with:

Linux에 파이썬 3.10 버전밖에 설치되어 있지 않아 오류가 생겼다.
pyenv는 여러 파이썬 버전을 관리할 수 있도록 도와주는 도구이다.
Linux를 기준으로 pyenv를 설치하는 방법은 다음과 같다.

1. pyenv를 시스템에 clone한다.
```bash
git clone https://github.com/pyenv/pyenv.git ~/.pyenv
```

2. pyenv 환경설정
```bash
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(pyenv init --path)"' >> ~/.bashrc
echo 'eval "$(pyenv init -)"' >> ~/.bashrc
source ~/.bashrc
```

[[linux shopt not found 오류|zsh를 사용하고 있었어서 마지막 줄에서 오류가 났다.]]

이후 'pipenv install' 명령어를 정상적으로 입력할 수 있었다.