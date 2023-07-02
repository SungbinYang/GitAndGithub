> 인프런의 강민철님의 [모두의 깃 깃허브](https://www.inflearn.com/course/%EB%AA%A8%EB%91%90%EC%9D%98-%EA%B9%83-%EA%B9%83%ED%97%88%EB%B8%8C/dashboard) 강의를 참조하였습니다.

## 버전 비교하기

이전에 소스트리에서 커밋했던 파일을 한번 비교해보자.

### 직전 버전과 비교하기

아래의 그림처럼 직전 버전은 소스트리 하단부분에 잘 나와있고 추가된것은 파란색으로 표기가 되어있는 것을 알 수 있다.

![](https://velog.velcdn.com/images/bini/post/3ef73846-7a69-45a0-beba-951d0707083c/image.png)

삭제된것은 아래와 같이 빨간색으로 잘 표기되어 있다.

![](https://velog.velcdn.com/images/bini/post/503820c9-c1d8-48ea-b3e1-d11f5970d02a/image.png)

### 버전별 비교하기

현재버전과 바로 그 직전버전과 비교는 별다른 조치 없이 아래 우측하단에 보는것과 같이 잘 표기가 되어 있다.

![](https://velog.velcdn.com/images/bini/post/11d281b1-6064-4bf9-b31d-1c695e8dc242/image.png)

아래의 그림처럼 특정버전과 비교할려면 비교하려는 cmd 버튼을 누른채 클릭하면 소스트리 하단에 나와있다.

![](https://velog.velcdn.com/images/bini/post/0a18909e-a50e-4189-b2b1-8309f6258a3e/image.png)

### 특정버전 파일 열기

아래의 그림처럼 특정버전의 파일을 열려면 해당 버전을 클릭후 좌측 하단의 파일의 오른쪽 마우스를 누른후 파일 열기를 누르면 된다.

![](https://velog.velcdn.com/images/bini/post/81cb6e98-4f4a-437f-89de-8934e15c0c26/image.png)

## 버전을 되돌리는 방법

만들어진 버전을 되돌리는 방법에는 크게 revert와 reset 2가지가 존재한다.

- revert: 버전을 되돌린 새로운 버전을 만드는 방법
- reset: 버전을 완전히 되돌리는 방법

> 💡 참고
> revert하는 방법의 중요한 의의: 기존에 버전은 유지한 채 버전을 되돌린 새로운 버전을 만드는것을 의의로 둔다.

여기서 reset은 또 3가지로 분류가 되는데 soft-reset, mixed-reset, hard-reset으로 분류가 된다.

- soft-reset: 저장소가 커밋했다는 사실을 되돌리는 리셋 방법
- mixed-reset: 스테이지로 추가했다는 사실을 되돌리는 리셋 방법
- hard-reset: 변경사항 생성했다는 사실까지 완전히 되돌리는 리셋 방법

> 🙋🏻 Q&A
> Q) 언제 revert를 쓰고 언제 reset을 쓸까?
> A) 모든 버전을 유지하려면 revert를 아니면 reset을 사용한다.

## revert, reset 실습

revert 실습과정은 해당 버전의 오른쪽 버튼을 눌러서 커밋 되돌리기를 누르면 된다.

![](https://velog.velcdn.com/images/bini/post/f8e2b078-475c-4f21-9360-8875664d8a91/image.png)

![](https://velog.velcdn.com/images/bini/post/3fefb6fe-a551-4f4d-a5a2-e5de357c98a1/image.png)

reset의 실습과정은 돌리고 싶은 버전의 오른쪽 버튼을 눌러서 master를 이 커밋으로 초기화 버튼을 누른 후 원하는 유형의 reset을 선택하면 된다.

![](https://velog.velcdn.com/images/bini/post/b9d232a9-e242-4d99-b8b6-9617b61dcc97/image.png)

![](https://velog.velcdn.com/images/bini/post/f98b350b-4189-46b7-8697-f6e286e8d2ba/image.png)
