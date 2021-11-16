### github 시작하기 (1)
***

<h3>기본 명령어 정리</h3>

지역 저장소로 관리할 폴더 우클릭 - Git Bash Here
<h4>깃 지역 저장소로 지정</h4>

```
git init
```
취소하려면 .git폴더 삭제 ` rm -rf .git`<br>

<h4>커밋 저자 등록</h4>

```
git config user.name "userName"
git config user.email "userEmail@email.com"
```
`-global` 옵션으로 전역으로 선언 가능
```
git config -global user.name "userName"
git config -global user.email "userEmail@email.com"
```


<h4>커밋에 포함될 파일 등록</h4>

```
git add 파일명
git add README.md
```
<h4>커밋하기</h4>

```
git commit -m "저장소설명"		 #새로운 커밋 생성
git commit --amend				#기존 커밋 수정
git commit --amend --no-edit 	#기존 커밋 설명 없이 수정
git commit --amend --author "username <email>"
```
> `-m` 명령어를 입력하지 않으면 새로운 커밋을 생성할 때 vi편집기로 여러줄의 커밋 메시지를 작성 할 수 있다.
>
> *커밋 메시지 작성할 때는...*
> *1. 제목과 본문 분리(내용 쓰기전 개행), 제목은 명령어로, 대문자로 시작하고 온점 쓰지 않기*
> *2. 커밋에는 하나의 문제만 다뤄서 수정 사항을 작은 단위로 관리할 수 있게 한다.(언제든 되돌릴 수 있게)*
> *3. 왜 커밋을 했는지, 무슨문제가 발생했는지, 적용한 해결책의 효과는 어떤지 작성*
> *4. 에러가 발생하지 않는 상태의 코드만 커밋*

<h4>커밋 상태 확인</h4>

```
git log
git log -p				#파일 단위에서 변경된 내용 보기
git log --patch			# git log -p와 동일
git log -5				#최근 커밋 로그 5개 보기
```

<h4>현재 프로젝트의 파일 상태 확인</h4>

```
git status
```

<h4>저장소에 커밋 등록</h4>

```
git push
```

<h4>저장소 파일을 로컬에 업데이트</h4>

```
git pull
```


<h4>리모트 저장소(깃헙) 등록</h4>

```
git remote add {저장소 주소}
```
> origin은 리모트저장소 이름 정한것


<h4>로컬 저장소에서 생성한 커밋을 깃헙에 등록</h4>

```
git push {저장소} {브랜치}
git push origin main
```
> main은 리모트저장소의 branch 이름 정한것

<br>

> <h5>.git/config 파일에서 설정파일 확인</h5>
>
* **repositoryformatversion** : 레포지토리 형식 및 버전 식별을 위한 내부 변수
* **filemode** : true or false 파일 변경 감지 여부 설정 (윈도우, 리눅스 동시 작업할경우 변경 안해도 변경됐다고 표시될 수 있음)
* **bare** : 코드 변경 작업 용도가 아닌 복사, 저장 용이면 true로 설정
* **logallrefupdates** : 깃 명령어 수행 로그 기록 활성화 git reflog 명령어로 기록된 작업 내역 확인
* **ignorecase** : 대소문자 구분여부 설정 true- 구분하지 않음
* **precomposeunicode** : 맥OS에서 한글파일명 인식문제 true로 설정하면 해결됨

<br>
<h4> 관리에서 제외할 파일 및 폴더를 지정</h4>

.gitignore 파일을 만들어서 제외할 파일 및 디렉터리 등록
```
Logs
*.Logsnpm-debus.log*

node_modules/
```

<h4>커밋 로그 형식 지정</h4>

```
git log --pretty=oneline
git log --preetty=format:"%h %an %s"		# %h: 짧은 커밋 해시, %an: 저자이름 %s: 커밋요약
git log --pretty=oneline --graph		#커밋 로그 가시적으로 보기
```

> ▼ --pretty 옵션에서 사용할 수 있는 출력 형식
>
| 형식  |    설명    |  형식  |      설명      |
|:----:|:------------:|:-----:|:--------------:|
| %H   | 커밋 해시     |%ae   |   저자 이메일   |
| %h   | 짧은 커밋 해시|%ar    | 저자 상대적 시각|
| %T   | 트리 해시     |%cn   |	커미터 이름	|
| %t   | 짧은 트리 해시|%ce   |	커미터 이메일	 |
| %P   |   부모 해시   |%cr   | 커미터 상대적 시각|
| %p   | 짧은 부모 해시 |%s   |	   커밋 요약	|
| %an   |   저자 이름  |      |	      |

<br>
<h4>명령어에 별명 붙이기</h4>

```
git config allias.별명 '바꾸기전명령어'
git config allias.history 'log--pretty=oneline'

```
