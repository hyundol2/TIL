<!-- TOC -->

- [Workbench 기본 사용법](#workbench-%EA%B8%B0%EB%B3%B8-%EC%82%AC%EC%9A%A9%EB%B2%95)
    - [새로운 커넥션 생성](#%EC%83%88%EB%A1%9C%EC%9A%B4-%EC%BB%A4%EB%84%A5%EC%85%98-%EC%83%9D%EC%84%B1)
    - [새로운 sql 파일 불러오기](#%EC%83%88%EB%A1%9C%EC%9A%B4-sql-%ED%8C%8C%EC%9D%BC-%EB%B6%88%EB%9F%AC%EC%98%A4%EA%B8%B0)
- [쿼리문 작성 및 실행법](#%EC%BF%BC%EB%A6%AC%EB%AC%B8-%EC%9E%91%EC%84%B1-%EB%B0%8F-%EC%8B%A4%ED%96%89%EB%B2%95)
    - [쿼리란?](#%EC%BF%BC%EB%A6%AC%EB%9E%80)
    - [Workbench에서의 쿼리문 실행방법](#workbench%EC%97%90%EC%84%9C%EC%9D%98-%EC%BF%BC%EB%A6%AC%EB%AC%B8-%EC%8B%A4%ED%96%89%EB%B0%A9%EB%B2%95)

<!-- /TOC -->

## Workbench 기본 사용법


### 새로운 커넥션 생성

기본 커넥션이 존재하지만 작업물에 따라 새로운 커넥션을 만들어 사용하면 관리하기가 편해진다고 한다

<br/>

![Untitled](../image/mysql/Untitled.png)

Workbench 프로그램을 처음 실행시키면 다음과 같은 화면이 나온다. + 를 눌러 새로운 커넥션을 만들자

<br/>

![Untitled](../image/mysql/Untitled2.png)

> + 를 누르면 다음과 같은 창이 열린다.
1. `Connection Name`에 본인이 사용할 이름을 작성하고
2. `Port` 번호와 유저네임을 확인한 뒤 
3. `Password` 에서 Store in Vault 버튼을 누르고 새로운 입력창이 열리면 설치 시 지정한 root의 비밀번호를 누르고 ok를 누른다.
4. 우측 하단 ok 버튼을 누르면 새로운 커넥션 생성이 완료된다

<br/>

### 새로운 sql 파일 불러오기

아직 스키마의 생성을 배우지 않았으므로 워크벤치에서 테스트 쿼리문을 실행해 보려면 예제 sql 파일을 불러와야 한다.

<br/>

![Untitled](../image/mysql/Untitled3.png)

1. 생성한 커넥션에 들어가면 다음과 같은 화면이 열린다.
2. `Administration` → `Data Import/Restore` 메뉴을 클릭한다.

<br/>

![Untitled](../image/mysql/Untitled4.png)

1. `Import from Self-Cpntained File` 체크
2. `...` 을 클릭해 원하는 sql 파일을 선택한다.
3. `Start Import` 를 클릭한다.

<br/>

![Untitled](../image/mysql/Untitled5.png)

1. Import Completed

<br/>

![Untitled](../image/mysql/Untitled6.png)

좌측에 위치한 `Schemas` 를 클릭하고 새로고침🔄 버튼을 누르면 추가된 데이터베이스를 확인할 수 있다.

<br/>

## 쿼리문 작성 및 실행법

### 쿼리란?

- 쿼리(Query)란 간단하게 얘기해서 데이터베이스에 정보를 요청하는 것이다.
- Query 단어 자체의 뜻은 ‘질의’이다. DB 서버가 구동이 되고 있는 환경에서 DB에 대한 명령문을 작업하여 원하는 정보를 요청하는 것이 쿼리라고 생각하면 되겠다

<br/>

### Workbench에서의 쿼리문 실행방법

![Untitled](../image/mysql/Untitled7.png)

1. 명령을 하고자 하는 스키마를 더블클릭
2. 하단에 현재 선택된 스키마를 확인할 수 있다
3. 쿼리 작성 공간에 쿼리문 입력
4. 실행 버튼을 눌러 쿼리문 실행
    1. 커서가 있는 1개의 쿼리문을 실행 시키려면 `Ctrl + Enter` 단축키 활용하자

다음과 같이 진행하면 쿼리문으로 요청한 데이터가 결과로 나온다