# TRL : Today Rosiee Learn
# GIT   
## GIT : 분산 버전관리 프로그램
* 코드 히스토리(버전)관리 가능한 도구, 과정 파악 가능, 변경사항 비교 및 분석

* 중앙 집중식(변경사항 - 중앙, 최신파일만 나) // 분산(변경,최신 모두 나에게 O)

  * 깃 추상화     
실제폴더 - a.txt    
→ add . : staging area (예비공간) ; 커밋하려는 의미있는 것들을 옮겨둔 공간  

    → commit -m ‘’ : staging area 에 있는 것들을 커밋


    .gitignore : 깃으로 관리하지 않겠어 
    
### GIT HUB : GIT을 이용한 저장소 서비스 
* 깃 허브 연결하기

    큰 흐름 : [ remote (깃 허브 서버 url) → push → [깃허브 repositories] → pull → clone ]

    → remote 와 clone은 처음에만 실행, 그 후로는 push / pull 만 실행
  
    ### ⇒ 이전 과정

  1) `git config` 로 이메일과 유저네임 연결

  2) `git commit -m` 으로 커밋

  3) `git log --oneline` 으로 확인
----
## Repository 생성 및 GIT PUSH

1. **GIT HUB** 우측 상단 + 버튼으로 **New repository**
2. Repository name 입력하고, create repository
3.  `git remote add origin url`로 깃 연결
 
    ⇒ remote 깃으로 원격으로 조종할 거야    
    ⇒ url 이 길어서 origin이라고 부를거야
4. git push origin master 로 깃에 push!
5. 깃 허브에서 확인
6. `git push -u origin master` 하면 설정이 저장되어, 그 후부턴 git push 만 해도 push 됨

     ⇒ 항상 마스터로 푸시할거야


---

## GIT CLONE : PULL

깃허브 활용하여 다른 폴더로 a.txt 파일을 pull 하기!

1. 폴더 생성하여 이동, pull 할 폴더에서 git bash 실행   
    (또는 git bash 새로 열어서 명령어로 생성 및 이동해도 O)
2. GIT HUB 에서 PULL 할 파일이 있는 repository 에서 url 복사
3. GIT bash 에서 `git clone url` 해서 클론  
     → cd repository name 하여 이동

    → ls 로 확인

    → `git log --oneline` 으로 클론된 것 확인


---
## Push / Pull
image.png
1. git_practice 에 변경사항(b.txt 파일 생성) 만들기
    
    `touch b.txt`
    
2. 상태 확인
    
    `ls` : 파일 생성 확인
    
    `git status` : 깃 상태 b.txt 변경 사항 확인
    
3. `git add .` 하여 변경사항 staging area 로 이동

4. `git commit -m` 로 커밋

5. `git log --oneline` 으로 확인 

6. `git push origin master` 로 푸시

7. git hub 에 올라온 것 확인~


- **git_practice_clone** 의 git bash 창에서 **pull**
1. `git log --oneline` 으로 확인
    
    → a.txt 만 커밋됨
    
2. `git pull` 로 당겨오기

3. `git log --oneline` 으로 다시 확인
    
    → b.txt 파일도 생김!