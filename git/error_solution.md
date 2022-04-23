# 오류 해결하기
-----
**20220423**

-----
## push 할 때 오류 발생
- 명령어
```
$ git pull https://github.com/devpcjin/WIL.git main
```
- 에러 내용
```
From https://github.com/devpcjin/WIL
 * branch            main       -> FETCH_HEAD
fatal: refusing to merge unrelated histories
```
- 해결 방법
```
$ git pull origin main --allow-unrelated-histories
```
----
