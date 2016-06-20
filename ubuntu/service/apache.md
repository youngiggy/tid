#[Ubuntu] 우분투 Apache(아파치) 이해
[source](http://webdir.tistory.com/196)

새로운 vhosts 적용
```
sudo a2ensite example.com.conf
sudo a2ensite test.com.conf
```

재시작
```sudo service apache2 restart```

설정 디렉토리 구조
```/etc/apache2```

설정파일 루트위치로, 설정파일들이 이 디렉토리 밑에 위치하고 있다.
```
/etc/apache2/apache2.conf
```

기본 설정파일로, 다른 배포판에서 httpd.conf를 기본 설정파일로 사용하고 있는데 우분투에서는 apache2.conf를 사용한다.
```
/etc/apache2/conf.d
```

고급설정 파일로, 다른 배포판에서 httpd.conf 파일 하나에 설정되어 있던 문자셋과 에러메시지, 보안과 관련된 설정등을 따로 따로 분리하여 conf.d 디렉토리밑에서 설정하고 있다. 또한 사용자가 설치하게 되는 Apache와 관련된 애플리케이션들의 설정파일들도 위치하게 된다.
```
/etc/apache2/envvars
```

apache2ctl 환경설정 파일이다.
```
/etc/apache2/httpd.conf
```

사용자의 특정 설정 파일로, 역사적으로 httpd.conf 가 기본설정 파일이였는데 지금은 빈파일이다. 사용자가 특정 설정을 부여해서 사용할 수 잇다.
```
/etc/apache2/magic
```

파일의 시작값(magic number) 데이터베이스. 이 값에 기반해 전송하는 파일의 MIME Type을 결정한다. 가급적 수정하지 말 것.
```
/etc/apache2/mods-available
```

사용가능한 Apache 모듈을 불러오는 곳이다.
```
/etc/apache2/mods-enabled
```

위의 /etc/apache2/mods-available 의 모듈중에 사용할 모듈을 심볼릭 링크로 추가하여 실제 동작하게 만든다.
```
/etc/apache2/ports.conf
```

Apache 서버의 서비스 포트 설정으로 http의 기본값 80 과 https의 기본값 443, 가상호스트의 포트들을 설정할 수 있다.
```
/etc/apache2/sites-available
```

서버에서 운영할 사이트의 설정파일이다.
```
/etc/apache2/sites-enabled
```


