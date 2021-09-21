# :cat2: About Git
*0919~0920 자체 연휴기간 휴식 아닌 휴식(Java season)*
<br/>

## 'C언어는 몰라도 깃허브는 알아야지!'
#### Git의 역할
1. 내 소스코드를 저장
2. 소스코드 공유
3. 프로젝트 협업 공간
<br/>
#### Git 사용방법
1. Git 설치 : https://git-scm.com/
2. 설치 완료 후 설치 위치로 이동하여 **Git bash** 오픈
3. Git bash 환경설정

  - Step 1 : usename 설정
  `git config --global user.name "your_name"`

  - Step 2 : email 설정
  `git config --global user.email "your_email"`
  (Github 계정 이메일을 작성해줘야 한다.)

  - Step 3 : 정보 확인하기
  `git config --list`
<br/>

### Githu 명령어 모음

##### 초기화
`git init`  추가할 파일 더하기

`git add .`
.(점) 은 모든 파일이라는 뜻으로, 모든 파일이 아닌 선택적으로 올리고 싶으면 add뒤에 파일 이름 붙여주면 된다 (예, git add index.html)
<br/>
##### 상태 확인 (선택 가능)

`git status` 히스토리 만들기

`git commit -m "first commit"`
-m 은 메세지의 준말.
뒤에 “” 안에 주고싶은 히스토리 이름을 주면 된다. 후에 히스토리 내용을 보고 어떤 내용을 커밋했는지 파악 가능하도록 이름을 작성하는 것 권장
<br/>

##### Github repository, 나의 local project와 연결

`git remote add origin https://github.com/bitnaGithub/firstproject.git`
이 명령어는 github에서 복붙
<br/>

##### 잘 연결됬는지 확인 (선택사항)

`git remote -v` 내가 연결한 주소값이 잘 뜨는지 확인!
<br/>

##### Github로 올리기

`git push origin master`
master 자리에는 <u>branch의 이름</u>이 들어가면 된다.
(branch 이름이 'main'이라고 하면 git push origin main 이라고 작성하면 된다.)
<br/>

##### Github에 계속 업데이트 하는 방법

`git add .` 추가할 파일 더하기

`git commit -m "first commit"` 히스토리 만들기

`git push origin master` Github로 올리기

>내 컴퓨터에 소스코드를 업데이트를 하고 싶으면 위의 3개의 과정을 계속 반복하면 된다.
<br/>

#### Github로 팀프로젝트 하는법 👨‍👩‍👧‍👦

##### Github에서 소스코드 다운로드

`git clone '주소' '폴더이름'`
- 주소는 깃허브에서 가지고 와야 한다.
- 폴더 이름은 선택사항이므로 없어도 되는 항목.
- 폴더 이름을 줄 경우, 그 폴더가 새로 생성이 되면서 그 안에 코드들이 다운로드
- 폴더 이름을 안 줄 경우엔, 깃허브 프로젝트 이름으로 폴더가 자동으로 생성되고 그안에 코드들이 다운로드
<br/>

##### Github에서 내 branch만들기

`git checkout -b 'branch 이름'`
내 branch에 소스코드 업데이트하기
```
git add .
git commit -m "first commit"
git push origin 브렌치이름
```
<br/>

##### master branch에 소스 가져오기(pull)

`git pull origin master`
pull을 하기 전에 우선 기존에 소스코드들을 commit 해놔야 한다.
<br/>

##### branch끼리 이동하는 법

`git checkout' branch 이름'`
내 branch에서 master branch로 이동을 하고 싶거나 다른 branch로 이동하고 싶으면 해당 명령어를 쓰면 된다
