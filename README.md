## git
왜 사용하는 것인가?
버전관리, 협업을 위해

## git init
- git 초기화
- git으로 관리하겠다.

- git에는 보안관련된 파일은 관리안하는것이 좋다. 해커로부터 털릴수있기 때문
## git status
- git 상태 확인

## git add
- git add . 모두 stage로 올리겠다.
- git rm cashed

## .gitignore
- git에서 관리 제외할 파일 설정 가능.

## git commit(약속하다)
- git commit -m "message"
- git commit -am "add와 message를 합칠 수 있다."
## git config user.name/user.email

## git diff
- 바뀐 부분을 알 수 있다.

## git log
- 커밋한 이력들을 볼 수 있다.

## vim 끄튼법 :q

## checkout
git checkout -- code1.txt
이렇게 하면 잘못 수정한 내역이 remote 내용으로 돌아옴.

## remote
- git remote add origin https://github.com/seyoungjoy/git.git
원격 저장소의 주소 설정
- git remote get-url origin
원격 저장소 주소 확인

## push
- git push origin master
원격 저장소 master에 업로드하겠다.

## pull
- git pull origin master
- 

## reset
