#brew


## 설치중 문제 해결
설치는 됐으나 /usr/local/share/systemtap에 심볼릭 링크를 못걸었다는 문구가 나올 때(대충 비슷한 문구다)
- sudo chown -R $(whoami) /usr/local/share/systemtap
- 권한이 없는 문제였음
- 그러게 에러 메시지 좀 유심히 보자 
