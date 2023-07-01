> 인프런의 강민철님의 [모두의 깃 깃허브](https://www.inflearn.com/course/%EB%AA%A8%EB%91%90%EC%9D%98-%EA%B9%83-%EA%B9%83%ED%97%88%EB%B8%8C/dashboard) 강의를 참조하였습니다.

## 로컬 저장소 만들기

먼저 이론적인 학습하기 전에 이전에 설치한 소스트리로 로컬저장소를 세팅해준 후 이론 학습을 하기로 한다. 여기서 로컬 저장소란 깃으로 관리되는 버전들이 모여있는 저장소를 의미하며 목적지 경로란 해당경로를 깃으로 관리한다고 정의한 것이다.

### 소스트리 로컬 저장소 생성

먼저 소스트리를 켜고 새로만들기라는 탭에 로컬저장소 생성이라는 버튼을 클릭한다.

![](https://velog.velcdn.com/images/bini/post/da194238-d79f-4918-8787-fad98ebd6f3f/image.png)

여기서 임의로 만든 폴더를 목적지 경로로 설정 후 생성하기 버튼을 클릭하면 아래와 같이 생성된다.

![](https://velog.velcdn.com/images/bini/post/ed8cdd46-f588-4fb1-845c-e157f6e34a17/image.png)

그리고 해당 디렉터리를 보면 .git이라는 파일이 생긴것을 볼 수 있다.

![](https://velog.velcdn.com/images/bini/post/9615d861-a796-49cf-9016-7bddf4a144c3/image.png)

그리고 소스트리의 생성된 로컬저장소를 클릭하면 다음과 같은 화면이 열린다.

![](https://velog.velcdn.com/images/bini/post/bb363945-ddff-4a24-b4bb-30707cd2c237/image.png)

이 화면에서 해당 목적지 경로의 버전 히스트로가 저장되고 관리된다.

### 정리

즉 특정 디렉터리를 목적지 경로로 로컬저장소로 만들면 해당 목적지 경로 안에 .git이라는 숨김폴더가 생긴다.
