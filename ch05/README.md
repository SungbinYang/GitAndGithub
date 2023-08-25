> 인프런의 강민철님의 [모두의 깃 깃허브](https://www.inflearn.com/course/%EB%AA%A8%EB%91%90%EC%9D%98-%EA%B9%83-%EA%B9%83%ED%97%88%EB%B8%8C/dashboard) 강의를 참조하였습니다.

## 깃 명령어를 알아야 하는 이유

> 💁🏻 소스트리는 일종의 보조도구일 뿐이다.
> 소스트리를 이용하지 않고도 얼마든지 능수능란하게 버전을 관리할 수 있다.

### 🙋🏻 소스트리로 학습을 했는데 왜 명령어로 한번 더 배워야 할까요?

우리가 소스트리로 깃을 학습하고 명령어로도 학습을 하게되면서 추후에 우리가 소스트리, 명령어를 능수능란하게 쓸수 있게 된다면 우리는 소스트리보다 명령어를 자주 사용할 것이다. 실무에서도 명령어를 훨씬 많이 사용한다.

소스트리를 이용한다면 처음에 배울때 시각적으로 보여서 학습하는데 있어서 편리하겠지만 실제 개발을 하고 변경사항을 생성하고 커밋을 하는 작업을 할때마다 소스트리로 들어가서 하는 것은 꽤나 번거로울 수 있다. 하지만 명령어는 한줄로 바로 끝낼 수 있다. vscode같은 IDE가 하단에 명령어를 제공하는 툴을 제공해줘서 쉽고 간단하게 할 수 있다.

또한 명령어밖에 이용할 수 없는 CLI상황이라면 소스트리를 이용하지 못하므로 명령어를 학습해야 할 것이다.

## 저장소와 버전 만들기

### git init: 로컬저장소 만들기

```bash
$ git init
```

git init 명령어는 소스트리에서 로컬저장소를 만들었던 것처럼 명령어로 로컬저장소를 만드는 명령어이다.

![](https://velog.velcdn.com/images/bini/post/98437ba1-e585-41aa-8b51-af26c6ce7d3b/image.png)

터미널에 특정 디렉터리에 가서 해당 명령어를 치면 위와 같이 나온다.
그리고 그 디렉터리로 가보면 빈 디렉터리에 .git이라는 숨김 디렉터리가 보일 것이다.

### git status: 작업 디렉터리 상태 확인하기

```bash
git status
```

git status 명령어는 현재 작업디렉터리 상태 확인 명령어이다.

먼저 실습을 해보자. 해당 디렉터리에 변경사항을 만들고 명령어를 입력하자.

![](https://velog.velcdn.com/images/bini/post/d7014e47-1d86-44be-bf09-7045e07516f1/image.png)

그럼 위와 같이 나오는데 추적하지 않는 파일에 우리가 방금 작성한 파일명이 나온다.

> 🙋🏻 추적하지 않는 파일이란?
> git이 기존에 변경사항을 추적하고 있지 않았던 파일 = 갑자기 생긴 파일

### git add: 스테이지에 올리기

```bash
git add 파일 이름
```

git add 파일이름을 작성하면 해당파일의 변경사항을 스테이지에 올리는 명령어이다.

![](https://velog.velcdn.com/images/bini/post/dd92a0f4-e36e-4fe9-9c95-734d2d1a3d49/image.png)

위와 같이 a.txt를 스테이지에 올리고 git status를 입력하니 위와 같이 나온다.

> 🙋🏻 커밋할 변경 사항이란?
> 커밋이 될 준비가 완료된 파일로서 a.txt가 스테이지에 올라갔다고 볼 수 있다.

그런데 예를 들어 여러 변경사항이 있고 이것을 동시에 스테이지에 올릴려면 변경사항이 발생한 파일명들을 전부 써줘야 할까? 뭔가 비효율적일 것이다. 그래서 아래의 명령어를 통해 한번에 변경사항들을 스테이지에 올릴 수 있다.

```bash
git add . // 현재 디렉토리에 발생한 모든 변경사항에 대해서 스테이지 추가
```

위와 같이 입력하면 아래처럼 나올 것이다.

![](https://velog.velcdn.com/images/bini/post/50305f25-a7e2-4e01-9b36-a3aadd2284f0/image.png)

### git commit: 커밋하기

```bash
git commit -m "커밋 메세지"
```

이제 스테이지에 올린 변경사항들을 버전으로 만드는 명령어는 바로 위에 처럼 작성해주면 된다.

![](https://velog.velcdn.com/images/bini/post/c9df53db-459b-40e3-b8bb-4773ae40fded/image.png)

그러면 새로운 버전이 생긴 것이다.

그런데 여기서 궁금한게 우리가 소스트리를 학습할 때 커밋 메세지는 위처럼 제목만 작성할 수 있지만 본문도 작성할 수 있다고 학습했다. 그러면 어떻게 본문 내용을 작성할까?

```bash
git commit
```

위의 명령어를 치면 아래와 같이 vim 화면이 나올 것이다.

![](https://velog.velcdn.com/images/bini/post/e222fddc-90ed-42aa-ad9f-469a471e7267/image.png)

> 🙋🏻 vim이란?
> 터미널 내부에서 파일을 수정하고 삭제할 수 있는 편집기

> 🛠 vim 사용시 주요 키
> a 혹은 i -> 입력모드 진입
> ESC -> 입력모드 탈출 (명령모드 진입)
> :w -> 작성한 파일 저장
> :q -> vim 나가기
> :wq -> 작성한 파일 저장하고 나가기

그러면 이제 커밋 메세지 제목과 본문 내용을 작성해보겠다.

![](https://velog.velcdn.com/images/bini/post/9865a481-32bd-48f7-b661-8553dbed6240/image.png)

위 처럼 작성을 해보자. a 혹은 i키를 눌러서 아래 INSERT가 나오면 입력모드가 진입이 된 것이고 커밋 메세지 작성을 한다.

그리고 작성을 했으면 :wq를 눌러 저장 후 나가자.

![](https://velog.velcdn.com/images/bini/post/1c876428-68dc-4cca-ab72-515fb120315a/image.png)

그런데 여기서 또 중요사항이 있다. git add와 git commit을 동시에 할 수도 있는 명령어가 있다.

```bash
git commit -am "커밋 메세지"
```

한번이라도 커밋을 했거나 깃이 변경사항을 추적하고 있는 파일에 대해서 위의 명령어를 통해 스테이지에 추가 및 커밋을 동시에 할 수 있다.

### git log: 커밋 조회하기

```bash
git log
```

지금까지 만든 버전 확인 명령어는 git log이다.

터미널에 git log를 치면 아래와 같이 나온다.

![](https://velog.velcdn.com/images/bini/post/b3448d80-f40d-4b92-a51b-305b69180bea/image.png)

해당 log를 빠져나가기 위해서는 q버튼을 누르면 된다.

## 커밋 다양하게 조회하기

앞서서 `git log` 명령어를 통해 아래와 같이 커밋들을 조회할 수 있다고 하였다.

![](https://velog.velcdn.com/images/bini/post/32b5be3e-0453-4a82-bed2-86aa7035cd38/image.png)

그런데 이 `git log` 명령어는 한눈에 와닿지 않고 깃로그가 너무 길어서 옵션을 통해 다양하게 출력할 수 있다.

### git log --oneline

커밋한 버전들을 한줄로 출력하는 명령어이다. 즉, 짧은 커밋 해시로서 모든 커밋이 1줄로 출력된다.

![](https://velog.velcdn.com/images/bini/post/2564bea8-4700-4760-9238-38fd9816100f/image.png)

### git log -p (git log --patch)

각각의 커밋이 어느 변경사항을 담고 있는지 출력해주는 명령어이다.

![](https://velog.velcdn.com/images/bini/post/18424ec0-1de6-409e-bfd2-ede31e47d833/image.png)

### git log --graph

깃 로그들을 소스트리처럼 브랜츠 그래프 형식으로 보여주는 명령어이다.

![](https://velog.velcdn.com/images/bini/post/3b82547e-8043-4e31-9bcf-74b715d8f1ff/image.png)

또한 다른 옵션과 섞어서 쓸 수 있다. 아래는 --oneline과 --graph를 섞어서 사용한 결과이다.

![](https://velog.velcdn.com/images/bini/post/d9bbd34d-b92a-4152-a333-ee58f98325ed/image.png)
