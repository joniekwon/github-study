### github 시작하기
***
지역 저장소로 관리할 폴더 우클릭 - Git Bash Here
<h4>깃 지역 저장소로 지정</h4>
```
git init
```
취소하려면 .git폴더 삭제 ` rm -rf .git`<br>
<h4>커밋에 포함될 파일 등록</h4>
```
git add 파일명
git add README.md
```
<h4>커밋하기</h4>
```
git commit -m "저장소설명"
```

<h4>커밋 상태 확인</h4>
```
git log
```

git commit --amend --autho
또는
```
git commit --amend --no-edit  #커밋 메시지 수정안하고 커밋
```

<h4>커밋 상태 확인</h4>
```
git log
```
<h4>커밋 저자 등록</h4>
```
git config user.name "userName"
git config user.email "email"
```
`-global` 옵션으로 전역으로 선언 가능

<h4>커밋 저자 정보 수정</h4>
```
git commit --amend --author "userName <email>"
```


<h4>리모트 저장소(깃헙) 등록</h4>
```
git remote add origin 주소
```
> origin은 리모트저장소 이름 정한것


<h4>로컬 저장소에서 생성한 커밋을 깃헙에 등록</h4>
```
git push origin main
```
> main은 리모트저장소의 branch 이름 정한것

<br>
> <h5>.git/config 파일에서 설정파일 확인</h5>
> * **repositoryformatversion** : 레포지토리 형식 및 버전 식별을 위한 내부 변수
> * **filemode** : true or false 파일 변경 감지 여부 설정 (윈도우, 리눅스 동시 작업할경우 변경 안해도 변경됐다고 표시될 수 있음)
> * **bare** : 코드 변경 작업 용도가 아닌 복사, 저장 용이면 true로 설정
> * **logallrefupdates** : 깃 명령어 수행 로그 기록 활성화 git reflog 명령어로 기록된 작업 내역 확인
> * **ignorecase** : 대소문자 구분여부 설정 true- 구분하지 않음
> * **precomposeunicode** : 맥OS에서 한글파일명 인식문제 true로 설정하면 해결됨

<br>
<h4> 관리에서 제외할 파일 및 폴더를 지정</h4>

.gitignore 파일을 만들어서 제외할 파일 및 디렉터리 등록
```
Logs
*.Logsnpm-debus.log*

node_modules/
```