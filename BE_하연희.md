# 1주차 git session
---
## 깃 초기 세팅
git init : 저장소 초기화
git remote add origin 개인 레포 주소
git remote add upstream 중앙 레포 주소
git remote -v : 연결 확인

git pull upstream 브랜치이름

## 브랜치 관리
git branch -M 브랜치이름 : 브랜치 만들고 스위치까지
git branch 브랜치이름
git switch 브랜치이름

git branch -d : 삭제 
** 브랜치 삭제 전에는 merge 가 필수 **

## push
git add .
git commit -m "커밋 메세지"
git pull upstream main : push 전에는 pull 이 필수
git push origin 현재 브랜치 이름

-> github 사이트에서 pull request / main에 Merge 해준 후
git switch main
git pull upstream main
git branch -d 사용한브랜치(merge 완)

---
## 장고
pip3 install pipenv
pipenv shell : 가상환경 켜기

pipenv install django
python -m django --version  : Django가 설치되었는지 확인

#### 올바른 위치에서 실행 (중요)
django-admin startproject project
python manage.py startapp main

## 서버
python manage.py migrate
python manage.py makemigrations

python manage.py runserver


### 장고 파이썬 오류 해결법
1. 윈도우 자체 마이크로소프트 마켓에서 파이썬 다운로드

2. 환경변수에 직접 패스 추가 (영구 적용)
    (C:\Users\flfkr\AppData\Local\Packages\PythonSoftwareFoundation.Python.3.13_qbz5n2kfra8p0\LocalCache\local-packages\Python313\Scripts)
-> 안 될 시

3. ~/.bashrc에 환경 변수 추가
    $ echo 'export PATH=$PATH:/c/Users/flfkr/AppData/Local/Packages/PythonSoftwareFoundation.Python.3.13_qbz5n2kfra8p0/LocalCache/local-packages/Python313/Scripts' >> ~/.bashrc
    $ source ~/.bashrc

을 통해 해결완료

### startapp main 오류 해결법
1. settings.py 코드 확인
2. manage.py 의 위치에서 가상환경 실행 (project 파일의 경로 확인)
3. 장고 설치 재확인