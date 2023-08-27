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

## 태그 관리하기

### git tag <태그>: 태그 추가하기

명령어로 커밋에 태그를 다는 방법은 아래와 같이 입력하면 된다.

```bash
git tag 태그이름
```

위와 같이 하면 최신 커밋에 태그가 붙여진다.

![](https://velog.velcdn.com/images/bini/post/0250b0fd-5bd1-49f9-9866-fb03af536e9b/image.png)

특정 커밋에 태그를 붙이는 방법은 아래와 같다.

```bash
git tag 태그이름 특정커밋해시
```

여기서 커밋해시는 긴 커밋해시를 적어도 되지만 짧은 커밋 해시를 입력해도 괜찮다.

### git tag --list: 태그 조회하기

깃 태그들을 조회하는 명령어는 아래와 같다.

```bash
git tag --list

git tag -l

git tag
```

위의 3가지 명령어중 하나를 입력하면 된다.

![](https://velog.velcdn.com/images/bini/post/21bdb490-ae9c-486a-a677-e1cde5d36c96/image.png)

### git tag --delete <태그>: 태그 삭제하기

태그를 삭제하는 명령어는 아래와 같다.

```bash
git tag --delete <태그>
```

![](https://velog.velcdn.com/images/bini/post/9080681d-ee45-4bda-9c2f-a08d6a9d5358/image.png)

## 작업 내역 비교하기

### git diff: 최근 커밋과 작업 디렉터리 비교하기

```bash
git diff
```

git diff는 지금까지 작업 디렉터리 변경사항과 가장 최신 커밋의 차이를 보여주는 명령어이다.

![](https://velog.velcdn.com/images/bini/post/0cf51b58-bef2-4b73-a67e-422e821a5747/image.png)

### git diff --staged: 최근 커밋과 스테이지 비교하기

```bash
git diff --staged
```

스테이지와 최근 커밋의 비교하는 명령어는 위와 같으며 이와 같은 명령어로 `git diff --cached`가 있다.

![](https://velog.velcdn.com/images/bini/post/66117157-ca08-4619-8772-3045c420a33c/image.png)

### git diff <커밋> <커밋> : 커밋끼리 비교하기

```bash
git diff <커밋> <커밋>
```

커밋끼리 비교하는 명령어는 위와 같다.

![](https://velog.velcdn.com/images/bini/post/77263b22-a298-4ab2-92a2-dbe2c0cad8ff/image.png)

> ⚠️ 주의
> 커밋끼리 비교할때 커밋의 순서가 중요하다 앞의 커밋은 뒤의 커밋보다 이전 커밋이여야 한다. 만약 반대로 하면 결과도 반대로 나올 것이다.

## 작업 되돌리기

### git revert <취소할 커밋> : 취소된 새로운 커밋 만들기

```bash
git revert <취소할 커밋>
```

revert를 명령어로 하는 방법은 `git revert <취소할 커밋 해시>`를 입력하면 된다. 커밋해시는 당연히 긴 커밋해시뿐만 아니라 짧은 커밋해시도 가능하다. 입력하게 되면 아래와 같이 나온다.

![](https://velog.velcdn.com/images/bini/post/ab2908a4-7e68-4f80-87ac-4c94faf618dc/image.png)

vim화면이 나오는데 자동으로 커밋 메세지를 적어주었기 때문에 :wq로 저장후 나가기를 하면 된다.

![](https://velog.velcdn.com/images/bini/post/32d6a706-750c-47af-9cf9-3d6abcff1b3e/image.png)

그리고 `git log -p`명령어로 확인하면 위와 같이 잘 revert가 되었다는것을 볼 수 있다.

### git reset <되돌아 갈 커밋>: 예전 커밋으로 되돌아가기

```bash
git reset <되돌아 갈 커밋>
```

revert와 다른 점은 reset 뒤에 되돌아 갈 커밋을 적어준다는 점이다. 그리고 소스트리때 배웠듯이 옵션이 soft, mixed, hard가 있다. 옵션이 없으면 기본은 mixed이며 옵션을 적어줄려면 reset 뒤에 --옵션명을 적어주면 된다.

![](https://velog.velcdn.com/images/bini/post/75babb27-3a10-4d0c-b18a-d3f8b8a67515/image.png)

## 작업 임시 저장하기

### git stash: 변경사항 임시 저장하기

```bash
git stash
```

현재까지 했던 작업을 임시저장하고 싶을 때 `git stash`명령어를 입력하면 된다.

![](https://velog.velcdn.com/images/bini/post/821f740b-04f0-42a9-8fba-f31c9b8a726c/image.png)

```bash
git stash -m "스태시 메세지"
```

여기서 추가적으로 위와같이 입력하면 커밋 메세지가 알수없게 기본으로 적용된다. 그래서 우리가 메세지를 커스텀하게 입력하고 싶으면 옵션 -m "스태시 메세지"를 적용하면 된다.

![](https://velog.velcdn.com/images/bini/post/daacc216-08fb-455b-a855-d872cc2770a3/image.png)

### git stash list: 임시저장된 작업내역 조회하기

```bash
git stash list
```

임시저장된 스태시 리스트를 확인하고 싶을 때 위와 같은 명령어를 입력하면 된다.

![](https://velog.velcdn.com/images/bini/post/df0cba54-366f-4d93-81a1-69c1968063f3/image.png)

> 🙋🏻 참고
> 여기서 주의할께 stash를 계속 하면 최신으로 stash한게 stash@{0}이 되고 이전의 stash@{0}은 stash@{1}이 된다.

### git stash apply <스태시>: 임시저장 된 작업 적용하기

```bash
git stash apply <스태시>
```

임시저장한 스태시를 적용하고 싶을 때 위와 같이 하면 된다. 여기서 스태시는 스태시 리스트의 앞의 stash@{0}과 같은 것을 작성해주면 된다.

![](https://velog.velcdn.com/images/bini/post/fd9b2335-998a-45f1-869b-5067bcd109f7/image.png)

### git stash drop <스태시>

```bash
git stash drop <스태시>
```

stash한 리스트들을 삭제할려면 위와 같이 작성해주면 된다. 여기서 스태시는 적용할때와 같이 stash@{0}과 같은 것을 작성해주면 된다.

![](https://velog.velcdn.com/images/bini/post/49a295ff-745d-43a5-8e9d-71b0825f5b33/image.png)

## 브랜치 관리하기

### git branch: 브랜치 리스트 확인

```bash
git branch
```

브랜치는 어떤게 있고 head는 어디를 가르키는지 확인하고 싶으면 위와 같은 명령어를 작성하면 된다.

![](https://velog.velcdn.com/images/bini/post/da56c0c1-a1ca-4ac7-8dbd-9a58dbc271e0/image.png)

### git branch <브랜치>: 브랜치 나누기

```bash
git branch <브랜치 이름>
```

브랜치 생성 명령어는 위와 같다. 위의 명령어를 입력하고 잘 생성되었는지 `git branch`로 확인해보자.

![](https://velog.velcdn.com/images/bini/post/041171ab-2076-4f6d-9495-24942239a99c/image.png)

### git checkout <브랜치>: 체크아웃하기

```bash
git checkout <브랜치 아름>
```

이제 생성한 브랜치로 작업을 진행할려면 체크아웃을 진행해야 한다. 체크아웃 명령어는 위와 같다.

![](https://velog.velcdn.com/images/bini/post/683a7e1f-0b58-4268-920e-c571c28a1789/image.png)

> ⚠️ 주의
> 여기서 주의사항이 있다. git log를 할때 주의를 해야하는데 예를 들어 foo 브랜치에 커밋을 진행하고 master 브랜치로 체크아웃후 log를 확인해보면 foo브랜치에서 만든 커밋로그들은 안 보일 것이다.
> ![](https://velog.velcdn.com/images/bini/post/6eb4b121-d47d-4c0c-a707-359a59fe78c0/image.png)
> 왜냐하면 `git log`명령어는 현재 브랜치 최신 커밋만 보여주고 다른 브랜치 커밋들은 안 보여주기 때문이다.
> 다른 브랜치 커밋도 확인하고 싶으면 `git log --branches`로 입력하면 잘 보일 것이다.
> ![](https://velog.velcdn.com/images/bini/post/219d4dca-a03c-4092-a55a-3f3c5cfaee0c/image.png)

여기서 더 하나 알아둬야 할께 브랜치 생성과 동시에 체크아웃을 진행할려면 아래와 같이 입력하면 된다.

```bash
git checkout -b <브랜치 이름>
```

### git merge <브랜치>: 브랜치 병합하기

```bash
git merge <합칠 브랜치 이름>
```

브랜치끼리 병합을 할려면 병합할려는 브랜치가 아닌 합쳐질 브랜치로 체크아웃 후 위의 명령어를 입력하면 된다.

![](https://velog.velcdn.com/images/bini/post/5de19955-6a3f-4ca1-b338-d38e91b7c58b/image.png)

### git branch -d <브랜치>: 브랜치 삭제하기

```bash
git branch -d <삭제할 브랜치 이름>
```

병합을 했으면 이제 합쳐진 브랜치는 사용 안 하면 삭제를 해줘야 할 것이다. 위와 같이 입력하면 브랜치 삭제가 가능하다.

![](https://velog.velcdn.com/images/bini/post/92532f70-cd3a-4406-9a65-7079245e5e8c/image.png)

### 충돌 해결하기

merge를 하다보면 충돌이 빈번히 발생하기 마련이다. 이제 명령어로 어떻게 충돌을 하는지 살펴보자. 일단 master브랜치에 b.txt를 생성후 bar 브랜치를 생성하고 각각 b.txt를 다르게 수정해보자.

![](https://velog.velcdn.com/images/bini/post/843bce11-4468-45b9-9595-b13b48a1a3a2/image.png)

그리고 merge를 진행하면 아래와 같이 경고표시가 뜰 것이다.

![](https://velog.velcdn.com/images/bini/post/84cf51eb-ca9a-47e6-afa4-7fd5c8a7f6f2/image.png)

그리고 b.txt를 가보면 소스트리때 봤던 것과 똑같이 아래와 같이 표시가 될것이다.

![](https://velog.velcdn.com/images/bini/post/4877c4db-b627-4cf0-9cf1-385c19ddc559/image.png)

여기서 head와 ===사이는 현재 브랜치의 수정한 파일의 내용이고 그 아래는 다른 브랜치의 내용이다. 여기서 우리가 선택을 해주면 된다. 예를 들어 Master를 반영한다고 하면 텍스트 파일에 Master로 적고 저장을 한다. 그리고 다시 커밋을 진행하면 된다.

![](https://velog.velcdn.com/images/bini/post/8933f587-2eb9-486f-ab4c-dd4d92d98b9d/image.png)

그러면 위와 같이 vi창에 자동으로 커밋 메세지가 작성이 될 것이고 :wq를 눌러 저장후 나오면 된다.

![](https://velog.velcdn.com/images/bini/post/9e4607a0-3769-4c1e-8bf2-1189a545b875/image.png)

이제 로그를 확인해보자.

![](https://velog.velcdn.com/images/bini/post/880e8578-e737-470a-8ff0-0fb19fbd2f33/image.png)

## rebase 하기

### git rebase <브랜치>: 브랜치 재배치 하기

```bash
git rebase <브랜치 이름>
```

일단 rebase실습에 앞서서 아래와 같이 커밋과 브랜치를 만들어둔다.

![](https://velog.velcdn.com/images/bini/post/7e1e5f20-439b-429c-ba7f-96081ce6f5de/image.png)

브랜치의 위치를 다시금 조정하는 명령어로 git rebase master로 하면 된다. 단, rebase할 때 rebase할 브랜치로 체크아웃이 되어 있어야 한다.

![](https://velog.velcdn.com/images/bini/post/676ff74d-d380-43a4-ab7b-6b0d39f3a1a0/image.png)

이제 log로 결과를 확인하자.

![](https://velog.velcdn.com/images/bini/post/b314f1b9-6e39-42ac-bad6-20da1918c013/image.png)
