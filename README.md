### github 오류 및 해결한 방법 정리

***

<br>
> Another git process seems to be running in this repository~~

위와 같은 오류 발생시 아래 명령어로 락걸린 파일 삭제해서 해결(ㅎ)
```
rm -f ./.git/index.lock
```


###  branch 생성 및 pull request
```
git branch joniekwon_week1
git checkout joniekwon_week1

~ 작업 ~

git commit -am "comimit message"
git push

git push origin joniekwon_week1

깃허브 돌아와서 compare pull request
제목, 내용 작성 후 create pull request
```
