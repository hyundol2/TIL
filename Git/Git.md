## Git?

분산버전 관리 시스템, 코드의 버전을 관리하는 도구이다.

<br/>

### Git 버전관리 기초

- Working Directory
    - 파일의 작업공간
- Staging Area
    - 버전으로 기록하기 위한 파일 변경사항의 목록
- Repository
    - 커밋(버전)들이 기록되는 곳

<br/>

### 기본 명령어

- `git status`
    - git 저장소의 파일 변경사항 확인
- `git add <file>`
    - 해당 파일을 staged 상태로 변경
- `git commit -m ‘<커밋메시지>’`
    - staged 상태의 모든 파일들을 버전으로 기록
    - -m은 메시지 추가 명령어
    - 메시지는 변경 사항을 나타낼 수 있도록 명확하게 작성해야 함
- `git log`
    - 현재 저장소에 커밋된 기록들을 조회
- `git config —global user.email "이메일 주소`
    - git 작성자의 email 정보 저장
- `git config —global user.name “이름”`
    - git 작성자의 이름 정보 저장

<br/>

### git짤막 팁

- .git 저장소가 있는 폴더는 이름 바꿔도 상관 x
- .git 폴더가 본체라고 생각하면 됨
- 대신 .git 폴더가 있는(이미 버전관리가 되고 있는) 다른 폴더로 경로를 이동하면 안됩니다.

<br/>

## GitHub, 협업의 시작

1. 먼저 GitHub에서 원격 저장소를 만들자!
2. 저장소 링크를 복사한 뒤 다음 명령어 실행

    ```bash
    git remote add origin <url>
    ```

3. 팀원의 저장소를 로컬로 가져올 수도 있음

    ```bash
    git clone <url>
    ```

4. 열심히 작업하고 커밋을 통해 버전으로 기록한 뒤 push하거나 팀원이 push한 버전을 pull하며 작업 진행

<br/>

### 명령어 모음집

- `git push <원격저장소> <브랜치>`
    - 원격저장소에 push
- `git pull <원격저장소> <브랜치>`
    - 원격저장소에서 pull
- `git clone <url>`
    - 원격에 있는 프로젝트를 내 로컬에서 시작하기 위해서는 git clonle을 한다!
    - 그냥 download zip을 선택하면  **버전**을 포함 원격저장소를 다운받는 것이 아닌 **가장 최신 버전의 파일**만을 다운 받는 것이다
- git remote add <원격저장소> <url>
    - 원격저장소 추가

```bash
git clone (url) : 원격저장소 복제
git remote -v : 원격저장소 정보 확인
git remote add <원격저장소> (url) : 원격저장소 추가(일반적으로 origin)
git push <원격저장소> <브랜치> : 원격저장소에 push
git pull <원격저장소> <브랜치> : 원격저장소로부터 pull
```

<br/>

- 깃헙은 파일을 관리하는 것이 아닌 **버전**을 관리하는 것.
깃헙 저장소에 올라간 특정 파일을 삭제하고 싶다? (잘못된 표현) → 삭제 상태를 add, commit, push해서 삭제된 버전을 올려라!

<br/>

### gitignore

- 생성한 뒤에 커밋을 원하지 않는 파일/폴더들을 이 안에 입력하면 관리X
- 일반적으로 들어가는 것들
    - 개발 언어
        - ex) 파이썬: venv/, 자바스크립트 : node_modules/
    - 운영체제
    - 텍스트 에디터 / IDE