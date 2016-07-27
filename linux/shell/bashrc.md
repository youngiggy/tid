#bashrc 설정

LANG 설정에 관한 문제 16.07.27
- svn update 시에 깨진 문자열이 보이고 UTF-8 어쩌고 하길레
- echo $LANG 해보니 ko_KR.eucKR로 되어 있었음
- export LANG=ko_KR.UTF-8하면 문제없이 실행됨
- 문제가 발생했던 건,
  - su -로 root로 로그인하고, 여기서 su xxx으로 로그인했기 때문
  - xxx는 LANG 설정이 없었고 기본으로 서버 설정에 맞춰가는데 UTF-8임
- 이를 해결하기 위해 xxx의 .bashrc에 LANG=ko_KR.UTF-8를 넣을까 했는데
  - 이 서버를 기준으로 모든 웹서버가 그렇게 설정된 상태이며
  - 적용을 위해선 많은 테스트가 필요할 것으로 보임