### git이란?
- 분산 버전관리 시스템으로 코드의 버전을 관리하는 도구이다
- 컴퓨터 파일의 변경사항 추적 가능, 같은 파일을 여러 명의 사용자와 동시에 작업이 가능하다

### SVN과 Git의 차이점은?
- SVN
    - 중앙 서버에 소스코드와 히스토리를 저장
    - 여러 개발 PC와 저장소에 분산하여 저장. 중앙 서버에 장애가 발생하여도 로컬 저장소에 커밋 가능, 로컬저장소들 이용하여 중앙 저장소의 복원 가능
    - 로컬 to 중앙, 중앙 to local 

### Git 버전관리 기초
- 크게 Working directory, Staging Area, Repository로 나눌 수 있다.
- Working Directory
    - 파일의 변경사항들이 위치함
- Staging Area
    - 버전으로 기록하기 위한 파일 변경사항들의 목록
- Repository
    - 커밋(버전)들이 기록되는 곳

### 기본 명령어들
- $git add <file>
    - 파일 변경사항을 Staging Area로 올려줌, 커밋 대기상태? Staged상태로 생각하면 될 듯
- $git commit -m ‘<커밋메시지>’
    - Staged 상태의 파일들을 커밋
    - -m은 메시지 추가 명령어
    - 메시지는 변경 사항을 나타낼 수 있도록 명확하게 작성해야 함
- $git log
    - 현재 저장소에 커밋된 기록들을 조회
- $git status
    - git 저장소에 있는 파일의 상태를 확인하기 위하여 활용
- 서명, 사용자 설정(최초 커밋때 필수로 해줘야 함)
    - git config —global user.email "본인 이메일"
    - git config —global user.name "본인 이름"

### 파일 관리 상태 라이프사이클

- Status로 확인할 수 있는 파일의 상태
    - Tracked - 이전부터 버전으로 관리되고 있는 파일 상태
    - Untracked - 버전으로 관리된 적 없는 파일 상태(파일을 새로 만든 경우)