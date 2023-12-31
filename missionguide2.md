# 리뷰 진행 방법
## PR 을 보냈다면 다음과 상태이다.
![image](https://github.com/LIN-KHU/linkhu-docs/assets/103228463/302698ae-1808-42d2-ba20-bfb2f4c30fcb)

### 1. 받은 피드백을 반영한다.
피드백을 반영한 후 add, commit, push 명령을 실행한다.
pull request를 보내 피드백을 받은 후 add, commit, push를 한 후 새로운 pull request를 보내지 않아도 된다.

앞서 보낸 pull request가 통합(merge)되지 않은 상태이기 때문에 같은 pull request를 재활용한다.

```
git status // 변경된 파일 확인
git add -A(또는 .) // 변경된 전체 파일을 한번에 반영
git commit -m "메시지" // 작업한 내용을 메시지에 기록
```
```
git push origin 브랜치이름
ex) git push origin step1
```
Linkhu에 보낸 PR은 자신이 fork 한 repository 의 commit 을 반영해주기 때문에 자신의 repository stepX 브랜치로 commit 하면된다.

### 2. 다음 미션 진행
리뷰를 몇 번 주고 받은 후 리뷰어가 Approve 해서 merge 한다면 다음 단계를 따라간다.
