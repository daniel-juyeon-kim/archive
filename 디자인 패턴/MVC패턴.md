# MVC

MVC(Model, View, Controller)는 각자 역할에 따라 분류한 디자인 패턴입니다.

각각의 역할은 다음과 같습니다.

- 모델 : 데이터와 비지니스(CRUD) 로직 처리
- 뷰 : 사용자에게 보일 레이아웃, 화면 처리
- 컨트롤러 : 사용자의 요청을 받아 모델과 뷰에 명령 전달 + 일부 비지니스 로직 처리

사진으로 보면 다음과 같습니다.

<img src="https://developer.mozilla.org/ko/docs/Glossary/MVC/model-view-controller-light-blue.png" width="600"/>
<span style="color:gray">출처 https://developer.mozilla.org/ko/docs/Glossary/MVC</span>

위 사진의 관계를 설명하면

- 뷰 : 사용자에게 보여는 뷰는 입력(요청)에 따라 컨트롤러로 요청을 전달합니다.
- 컨트롤러 : 
    - 요청에 따라 모델(비지니스, 데이터)에 적절한 요청을 보냅니다.
    - 단순히 데이터를 다른 형태로 나타내기 위해 뷰를 업데이트합니다. (이때 모델과의 통신은 없습니다.)
- 모델 : 데이터, 비지니스 로직 수행 후 뷰에게 업데이트 내용을 알리게 됩니다.

프로젝트의 구조가 복잡한 경우 모델은 데이터베이스에 대한 비지니스 로직 처리, 컨트롤러에서 문자 발송과 같은 비즈니스 로직을 처리합니다.