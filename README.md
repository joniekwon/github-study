### github 오류 및 해결한 방법 정리

***

<br>
>Another git process seems to be running in this repository~~

위와 같은 오류 발생시 아래 명령어로 락걸린 파일 삭제해서 해결(ㅎ)
```
rm -f ./.git/index.lock
```