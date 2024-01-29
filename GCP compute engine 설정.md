# GCP compute engine 생성, 설정과정

## GCP 생성 순서

> [GCP 링크](https://cloud.google.com/free?utm_source=google&utm_medium=cpc&utm_campaign=japac-KR-all-en-dr-BKWS-all-core-trial-EXA-dr-1605216&utm_content=text-ad-none-none-DEV_c-CRE_668690472449-ADGP_Hybrid%20%7C%20BKWS%20-%20EXA%20%7C%20Txt%20~%20GCP_General_core%20brand_main-KWID_43700077514871058-kwd-87853815&userloc_1009846-network_g=&utm_term=KW_gcp&gclid=CjwKCAjw6eWnBhAKEiwADpnw9vo8E8Zo5cxQpQlk-BXha3bUaHq0VsJIToFXmv1Q7yoDFcmES0DxVxoCIL0QAvD_BwE&gclsrc=aw.ds&hl=ko)

1. 콘솔로 이동
2. computer engine
3. 인스턴스 생성
4. 옵션 설정

## GCP 인스턴스 SSH 연결 과정

1. GCP인스턴스의 SSH키 설정</br>
https://cloud.google.com/compute/docs/instances/connecting-advanced?hl=ko#provide-key
2. SSH 키 생성</br>
https://cloud.google.com/compute/docs/connect/create-ssh-keys?hl=ko

다음과 같이 키를 만들게 되면 `~./ssh` 폴더 내부에 파일 두개가 추가되어 있다.

해당 파일을 인스턴스에 공개키로 등록해야 한다.

### 인스턴스에 SSH 공개키 등록

> `~./ssh`에 있는 파일이 ssh, ssh.pub로 가정

1. `cat ssh.pub` 내용 복사
2. 생성한 GCP 인스턴스의 설정
3. 메타데이터
4. SSH 키 등록

### 인스턴스 접속

`ssh -i ssh 사용자이름@인스턴스외부IP`

### GCP 배포 주의할 점

GCP 인스턴스에 ip를 클릭하면 https 로 접속한다. 서버에 https 설정을 한게 아니라면 http로 접근해야한다.

## 기타 설정

### zsh 설치

> 기본적으로 bash가 설치되어 있다. 편의상 zsh를 사용한다.

1. `apt-get install zsh` zsh설치
2. `chsh -s $(which zsh)` 기본 쉘 변경

다시 bash 쉘로 복귀하고 싶을때는 which bash로 바꾸면 bash쉘의 경로로 설정한다.

### zsh 커스터마이징

#### oh-my-zsh

https://github.com/ohmyzsh/ohmyzsh

`vi ~/.zshrc` 를 통해 zsh의 설정을 변경할 수 있다.

#### powerlevel10k

1. README.md > installation > oh-my-zsh </br>
https://github.com/romkatv/powerlevel10k?tab%253Dreadme-ov-file#oh-my-zsh

2. README.md > getting started </br>
https://github.com/romkatv/powerlevel10k?tab%253Dreadme-ov-file#getting-started

<!-- # npm npx

npm i 기본적인 노드 패키지 설치 => 명령어 사용 불가
npm i -g 노드 패키지 전역 설치 => 명령어 사용 가능
npx i 전역설치 x 하지만 npx 명령어로 명령어 실행 가능 -->
