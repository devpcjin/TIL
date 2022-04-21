# git
20220420 TIL

---

## Git 저장소 만들기
### 기존 디렉토리를 Git 저장소로 만들기 (Local)
- ```cd``` 명령어를 통해 local 저장소로 이동
``` linux
$ git init
```
- ```.git```폴더 생성 확인

### 기존 저장소를 clone하기
``` linux
$ git clone <github-repo> <local directory>
```

## branch
- branch 생성하기

    ``` linux
    $ git branch <branchname>
    ```
- branch 전환하기

    ``` linux
    $ git checkout <branch>
    ```
- branch merge 하기

    ``` linux
    $ git merge <commit>
    ```

- branch 삭제하기

    ``` linux
    $ git branch -d <branchname>
    ```
------------
20220421

------
## Branch 확인하기
- 현재 내가 위치한 Branch 확인
    ``` linux
    $ git branch
    ```
    -  원격 저장소의 브랜치 확인
        ``` linux
        $ git branch -ㄱ
        ```

    - 브랜치의 마지막 커밋 메세지 확인
        ``` linux
        $ git branch -v
        ```

## 원격 Branch로 이동하기
-
    ``` linux
        $ git switch -t origin/[remote Branch]
    ```
