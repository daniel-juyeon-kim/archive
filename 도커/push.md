# 도커 이미지 저장소

## DockerHub에 push

- [도커](https://hub.docker.com/)

위 링크에서 > Create Repository

설정을 마치고 레포지토리를 만든다. 레포지토리를 만들면

```shell
docker push 사용자_아이디/레포지토리_이름:tagname
```

이라는 쉘 명령어가 나온다.

`사용자_아이디/레포지토리_이름`에 해당하는 이미지를 생성하고 로그인 후 docker push하면 정상적으로 업로드 된다.

```shell
# 1 도커 로그인
docker login

# 2 도커 이미지 생성 (이미지의 이름은 사용자_아이디/레포지토리_이름:tagname 여야 한다.)
...

# 3 이미지를 dockerhub에 push
docker push 사용자_아이디/레포지토리_이름:tagname
```

업로드가 된 것을 확인할 수 있다.

## GitHub에 push

1. 토큰 발급
   1. 전역변수 설정
   2. `echo $CR_PAT | docker login ghcr.io -u USERNAME --password-stdin`
2. github > profile > packages > containers > learn more\
3. `ghcr.io/NAMESPACE/IMAGE_NAME:latest` 에 해당하는 이미지 생성
4. `docker push ghcr.io/NAMESPACE/IMAGE_NAME:latest`

### Github 저장소와 package 연결

1. package > connect Repository
2. 해당 레포의 package에 연결한 패키지가 추가된 것을 확인할 수 있다.
