# Git 활용 및 Branch 전략
start Github

#Mac에서 설치하기

1. 터미널 접속
2. "git --version" 입력시 없으면 설치, 있으면 버전 출력  

#Github 명령어
% git add .                #1차 가상공간 추가
% git commit -m "메세지"     #가상공간에 최종 저장
% git push origin master   #Github 파일 업로드 (master branch 가 main으로 생성되어 있을 수 있음 에러시 확인)
% git pull origin master   #Github 파일 다운로드 
% git remote               #로컬저장소와 원격저장소 연결 확인
% git branch -v            #현재 branch 상황

#Git을 통한 초기화 방법
1. 기존 히스토리 삭제
  % rm -rf .git 
2. 새로운 git 설정
  % git init
  % git add . 
  % git commit -m "TEST"
3. 저장소 연결 및 강제 Push
  % git remote add origin
  % git push -u --force origin master

#Git Branch Flow (효과적으로 나누고 관리하기)
 - master 
  : 제품으로 출시되는 브랜치 release가 완료된 경우 merge 하며 버전 태그 부여
 - develop
  : 출시전 최종단계 개발소스 브랜치
 - feature (Issue_number) or (feature_name)
  : 기능별 브랜치
 - release (version_number)
  : develop 단계에서 feature 를 Merge 하여 releases branch 작성하여 QA, 테스트 진행
 - hotfix (Issue_number)
  : master 단계에서 문제 발생시 긴급 생성하는 branch (완료 후 develop, release,master 브랜치에 적용)
https://k39335.tistory.com/82  하단 이미지 

▶︎ 항상 존재하는 브랜치 : master
▶︎ 필요에 따라 생성하는 브랜치 : feature, hotfix, release (merge 된후 삭제)


rebase와 force push 의 위험성 때문에 master, develop, release 브랜치 단계에서 force push 는 막아두고 사용
우아한 형제들

Hotfix 브랜치에서 구체적인 동작에 대해서 추가적으로 공부필요

#Github Branch Flow(간소화)
 - master
  : 메인 노드 - 머지되면 배포 진행
 - feature
  : issue 발생시 master 브랜치에서 feature 브랜치를 생성하여 개발,피드백,테스트가 충분히 이루어진 뒤에 merge

 master 브랜치 pull > 개발 > 테스트&피드백 > 머지 

참고자료
https://hyeon9mak.github.io/git-branch-strategy/ 
https://tecoble.techcourse.co.kr/post/2021-07-15-git-branch/