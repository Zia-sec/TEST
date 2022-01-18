# Git 활용 및 Branch 전략
start Github

#Mac에서 설치하기

1. 터미널 접속
2. "git --version" 입력시 없으면 설치, 있으면 버전 출력  

#Github 연동
% git add .                #1차 가상공간 추가
% git commit -m "메세지"     #가상공간에 최종 저장
% git push origin master   #Github 파일 업로드 (master branch 가 main으로 생성되어 있을 수 있음 에러시 확인)
% git pull origin master   #Github 파일 다운로드 
% git remote               #로컬저장소와 원격저장소 연결 확인


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