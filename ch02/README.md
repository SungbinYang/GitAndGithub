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

## 작업 임시 저장하기

누군가 작업했던 것을 임시저장하고 싶을 때가 있다. 예를들어 작업중에 PM분이 더 급한건이 있어서 이것부터 처리해달라는 경우가 있을 수 있고 내가 작업했던 파일이 잘 만들어져서 어디선가 재활용이 가능할것 같은 것들을 임시저장할 수 있다.

소스트리에서는 이런 경우에 스태시라는 것을 활용할 수 있다. 먼저 변경사항을 만들고 우측 상단에 스태시를 클릭해보자. 그리고 메세지와 적고 스태시를 하면 왼쪽 메뉴부분에 치워두기 부분에 내가 작성한 메세지가 나오는것을 확인이 가능하다. 이것을 더블클릭해서 복원도 가능하고 오른쪽 마우스 클릭해서 삭제도 가능하다.

일단 아래와 같이 변경사항을 만들어보자.

![](https://velog.velcdn.com/images/bini/post/04c915a9-b27b-4831-8924-3ce42ff63fc2/image.png)

다음에 우측 상단에 스태시라는 버튼을 클릭하고 아래와 같은 팝업이 뜨면 메세지를 자세히 적고 스태시를 클릭해보자.

![](https://velog.velcdn.com/images/bini/post/a4636963-50de-452f-a541-cc4b6096e3d4/image.png)

그러면 아래와 같이 작업공간은 깨끗해질것이고 좌측에 치워두기에 내가 임시저장한것을 볼 수 있을 것이다.

![](https://velog.velcdn.com/images/bini/post/a32bc2df-7257-41eb-a2b3-4a643294af83/image.png)

그리고 임시저장한것을 되돌리려면 치워두기의 임시저장한 목록을 더블클릭하여 되돌리면 된다.

![](https://velog.velcdn.com/images/bini/post/637721b0-a371-44e9-be9f-e09bb6cbad1f/image.png)