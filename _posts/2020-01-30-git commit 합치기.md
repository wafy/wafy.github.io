git 커밋메세지 합치기
===

PR 보낸 커밋메시지 합치기
---

PR을 보낸 commit 중 한개로 합쳐 다시 commit해야 하는 상황이 발생하였다.

아래는 rebase 명령어를 사용하여 commit 한 방법을 정리하였다.

```
git rebase -i upstream/develop 

```

vim  에디터 창에서 이 나오고 합치고 싶은 commit 메세지 앞에
s 또는 squash를 입력 한후 vim 에디터 종료

```
git push origin --force
```


origin에 push한 commit 메세지 합치기
---

```
git rebase -i 1615fad(합치고 싶은 커밋의 부모 HEAD 값

```

vim  에디터 창에서 이 나오고 합치고 싶은 commit 메세지 앞에
s 또는 squash를 입력 한후 vim 에디터 종료

```
git push origin --force
```
