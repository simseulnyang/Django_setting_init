# Django_setting_init
Django 프로젝트 시작 시 기본적으로 설정하는 부분

## 1. poetry setting
= 참고 블로그 : <a href="https://blog.naver.com/wooy0ng/222988404966">우용이 블로그 - (tip) Poetry 파이썬 패키지 관리도구</a>

1-1. 프로젝트 생성
- 명령어를 실행하는 현재 폴더에서 poetry 프로젝트 생성 절차가 진행된다.
- `Would you like to define your main dependencies interactively? (yes/no) : `   => yes 입력하면 패키지 추가 가능
- 버전 관리 환경이 세팅되며 pyproject.toml 파일이 생성
```
$ poetry init
```

<br>

1-2. poetry 활성화
- 알아서 virtualenv를 만들어서 shell로 activate된다.
```
poetry shell
```

<br>

1-3. 라이브러리(패키지)install
- shell을 실행시켜 가상환경 진입에 성공하였다면 아래의 명령어를 입력하여 pyproject.toml에 저장된 내용에 기반해 라이브러리를 설치할 수 있다.
- 오류가 뜬다면 오류 내용에 해결 방법을 자세히 설명해주기 때문에 그대로 따라가면 된다.
```
poetry install
```

<br>

1-4. 라이브러리(패키지) 추가
- 사용자가 poetry 환경에서 개발을 하다가 라이브러리나 패키지를 추가하고 싶은 것이 생긴다면 아래의 명령어를 입력해 라이브러리 또는 패키지를 추가할 수 있다.
```
poetry add 추가할패키지(라이브러리)명
```

<br>

1-5. 라이브러리(패키지) 삭제
- pyproject.toml 파일에 삭제하고자 하는 패키지가 명시되어 있어야 한다.
```
poetry remove 삭제할패키지(라이브러리)명
```

<br>

1-6. 가상환경 내에서 파이썬 명령어 실행
- 보통 pip와 같은 명령어는 애초에 전역으로 설치되도록 설계되어있어, 무작정 pip를 사용하게 되면 후에 poetry와 의존성 문제로 충돌할 가능성이 있다.
- 때문에 poetry에서는 가상환경 내에서 명령어가 실행될 수 있도록 'run' 명령어를 지원해준다.
```
poetry run 명령어
```

<br>

1-7. poetry lock
- poetry.lock 파일은 pyproject.toml과 동일한 의존성을 가지고 있다.
- 누군가가 poetry 가상환경에서 poetry.lock 파일을 가지고 있다면 poetry.lock 파일을 만든 사람의 프로젝트 의존성을 동일하게 따라가게 된다.
- 팀 프로젝트 진행 시 GitHub repo에 poetry.lock 파일을 추가하는 것을 권한다.
- poetry.lock가 있는 폴더에서 poetry install 명령어를 사용해 라이브러리를 설치할 경우 의존성을 고려하여 설치해주게 된다.

- poetry.lock은 사용자가 임의로 변경할 수 없으며 pyproject.toml 파일을 수정(생성)한 후 아래의 명령어를 입력하면 poetry.lock을 수정(생성)할 수 있다.
```
poetry lock
```
