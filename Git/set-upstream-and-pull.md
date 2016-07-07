#upstream 셋팅하기
참고링크
- [3.5 Git 브랜치 - 리모트 브랜치](https://git-scm.com/book/ko/v2/Git-%EB%B8%8C%EB%9E%9C%EC%B9%98-%EB%A6%AC%EB%AA%A8%ED%8A%B8-%EB%B8%8C%EB%9E%9C%EC%B9%98)

upstream 설정
`
git remote add upstream 깃헙링크  
git remote -v
`

upstream에서 가져오기(pull)
- pull은 fetch 후 merge한 것과 같다
`
git pull upstream master
`
`
git fetch upstream master 
git merge upstream/master origin/master
`
