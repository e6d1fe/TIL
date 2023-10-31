# Cherry-Pick

다른 브랜치에 있는 커밋을 선택적으로 적용시키는 것  
예) `develop`이라는 브랜치를 파서 기능 1, 기능 2, 기능 3을 구현했는데 지금 당장 기능 2만을 publish해야 하는 상황  
➡️ 브랜치를 새로 판 후 기능 2 관련 커밋만을 따 와서 push & PR 요청!

```
$ git checkout main
$ git checkout -b cherrypick
$ git cherry-pick commitID
$ git push origin cherry
```

#### 하나만 따 오고 싶을 때

```
$ git cherry-pick commitID1
```

#### 여러 개를 따 오고 싶을 때

```
$ git cherry-pick commitID1, commitID2, commitID3

$ git cherry-pick commitID1..commitID3
```

### conflict가 발생한다면

1. conflict 해결하기 위해 코드 수정
2. `git add`로 수정된 코드 add
3. `git cherry-pick --continue`
