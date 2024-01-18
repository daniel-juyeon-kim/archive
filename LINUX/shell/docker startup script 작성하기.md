# docker startup script 작성하기

## startup script 설정

zsh 기준 `.zlogin` 파일을 통하여 쉘이 로그인된 상태일 때 해당 파일에 있는 스크립트를 실행한다.

### 스크립트 작성

docker login에 대한 스타트업 스크립트를 설정하고 싶다.

`.zlogin` 파일을 `.zshrc`가 있는 경로에 생성하고 아래의 스크립트를 작성한다.

#### zshrc

```shell
export CR_PAT="키값"
```

#### zlogin

```shell
if [[ -o login ]]; then
  echo $CR_PAT | docker login ghcr.io -u USER_NAME --password-stdin
else
  echo "This is not a login shell"
fi
```

로그인 상태일 때 실행할 스크립트를 if 블록 내부에 작성한다.

작성 후 새 터미널을 실행하면 잘 동작하는 것을 확인할 수 있다.
