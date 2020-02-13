PR된 커밋에 특정파일 제거
===

origin에 push한 커밋중 특정 파일을 빼고 싶다면..

```
git back
git reset head^
git status
git commit
git push origin -f
```
