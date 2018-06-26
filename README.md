# mybatis-query
Mybatis Query 추출 프로그램입니다. 
SI 프로젝트 중에 디버그용으로 만들었습니다. Mybatis 생성되는 Query가 include 나 with 그리고 if 문 등으로 쉽게 만들수 없을 때 Query만 간단하게 추출하는 프로그램입니다. 
원래는 eclipse에 java project로 만들었지만 단순한 설치를 위해서 gradle 로 동작하도록 만들었습니다. 
gradle eclipse 명령어를 이용해서 eclipse java project로 변환이 가능합니다. 



## 0.Prerequisites
- Java 1.8
- Gradle

DB는 따로 필요하지 않습니다. 

## 1.실행 방법 
```
gradle run
```

## 2.사용방법 

1. query.xml 파일에 사용하던 query로 변경 혹은 사용하던 query xml 파일을 resources 폴더에 옮겨 놓은 후에 그 위치를 mybatis-config.xml에 반영

2. 추출하고 싶은 Query id를 반영하여 소스를 수정 

```java

    //App.java
//Query id를 입력
String query ="query.sample1";

HashMap<String, Object> obj =new HashMap<String, Object>();
//Query 실행 parameter 입력 
obj.put("date1", "2018-08-06");
//obj.put("date2", "2018-08-07");

```

3. 프로그램을 실행(gradle run)하면 sql 폴더에 관련 Query가 추출된다.