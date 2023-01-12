# git의 개념 (2023-01-12)

- 분산 버전 관리 시스템
- 중앙 관리 시스템 vs 분산 버전 관리 시스템
- [git 한글 설명서](https://git-scm.com/book/ko/v2/Git%EC%9D%98-%EA%B8%B0%EC%B4%88-%EC%BB%A4%EB%B0%8B-%ED%9E%88%EC%8A%A4%ED%86%A0%EB%A6%AC-%EC%A1%B0%ED%9A%8C%ED%95%98%EA%B8%B0)  

## git 저장소 만들기
- git init (앞으로 git으로 관리 하겠다. git 레포 만들기)
- git config --global user.name ChangJae-YOO (git 설정에 이름을 넣어줌)
- git config --global user.email dondegi5@gmail.com (git 설정에 이메일을 넣어줌)

## git 수정하고 저장소에 저장하기
- git add filename (file을 추적하겠다고 하는 명령어)
- git commit -m adding file


## 커밋 히스토리 조회하기
- git status (현재 상태를 알려줌. untarcked, tracked, modified, unmodified)
- git log (commit 현황을 알 수 있음) (option : --oneline, 등등... 한글 설명서 참고)
- git diff (track 중이지만 변화가 생긴 얘를 출력해줌)

## 되돌리기
- git commit --ammend (가장 최근 커밋한 커밋에 지금 add 된 사항들을 다시 커밋해줌)
- git reset HEAD file (add 한 파일을 unstaged로 변경 해 줌.)

## 연결하기
- git remote add origin https://github.com/ChangJae-YOO/Today-I-Learned.git (origin이란 등록이름으로 주소를 원격 연결 )
- git remote -v (연결 확인)

## push, pull
- git pull origin main
- git push origin main
