#mysql에서 스키마와 comment를 같이 보기

- 간단히 comment를 보려면 `show create table 테이블명` 하면 된다
- DESC와 함께 comment를 보고 싶다면,
  - [INFORMATION_SCHEMA COLUMNS Table](http://dev.mysql.com/doc/refman/5.7/en/columns-table.html)을 열어보자
- 위키 문서 포맷에 맞추기 위해 
  - 간단히 필요한 필드만 골라보자
    - `SELECT ORDINAL_POSITION AS '순서', COLUMN_NAME, COLUMN_TYPE AS _Type, COLUMN_DEFAULT AS _Default, IS_NULLABLE AS _Nullable, COLUMN_KEY AS _Key, COLUMN_COMMENT AS _Comment, '' AS MEMO FROM information_schema.columns WHERE table_name = '테이블명';`
  - PHPStorm에서 Data Extractor를 HTML로 하고
  - test.html에 붙여넣기 & 브라우저 새로고침
  
