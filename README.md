# git
- 버전관리, 협업을 위해 사용

## TroubleShooting
- [repository not found error](/troubleShooting/repository-not-found.md)

### 다른 장소에 있는 레포 미러링하기
- clone의 옵션은 3가지가 있다.
  - clone(non-bare) : 기존 커밋 로그 불필요, 레포만 복사
  - clone --bare : 기존 커밋 로그 필요, 브랜치 모두 들고옴
  - clone --mirror : 기존 커밋로그(숨어있는 녀석들까지)와 브랜치 모두를 들고옴(기존 레포와  같은 환경)

1. 클론할 레포를 클론
```
$ git clone --mirror https://github.com/EXAMPLE-USER/REPOSITORY-TO-MIRROR.git
```
2. mirror한 폴더 위치에서 옮길 remote url을 설정
```
$ cd REPOSITORY-TO-MIRROR
$ git remote set-url --push origin https://github.com/EXAMPLE-USER/MIRRORED
```
3. 옮길 url에 push
```

$ git push --mirror
```

- reference
  - https://docs.github.com/en/repositories/creating-and-managing-repositories/duplicating-a-repository

### 동시에 두 개의 다른 레포에 push 하기
1. `git remote add` 명령어를 통해 push 되는 remote가 2개로 설정되면 된다.
```
git remote set-url origin --push --add [git url]
```
<img width="486" alt="image" src="https://user-images.githubusercontent.com/85421850/197744692-2d56f503-28fb-4b34-981b-dd9a11103653.png">

- reference
  - https://twofootdog.tistory.com/42
## concept
- 


## git init
- git 초기화
- git으로 소스를 관리하겠다 선언.
- (주의!) git에는 보안관련된 파일은 관리안하는것이 좋다. 해커로부터 털릴수있기 때문.

## git status
- git 상태 확인

## git add
- `git add .` : 모두 staging area에 올리겠다.

## .gitignore
- git에서 관리 제외할 파일 설정.

## git commit
- `commit` : 영어 뜻 ~를 적어두다
- 코드 변화를 저장소에 기록하다라는 뜻으로 개발 중인 코드의 이력을 생성할 수 있다.
- `git commit -m "message"`
- `git commit -am "message"` : git add와 commit을 동시에 실행.

## git config
- `git config --list` : git 계정 정보
- `git config user.name`
- `git config user.email`

## git log
- 커밋한 이력들을 볼 수 있다.

## 터미널에서 vim 끄는법
- `git log` 명령시 control+c로 안 나가지고 `:` 콜론 깜빡거리는게 vim 모드로 들어가서 그런거임.
- q 누르면 종료가능

## rollback
### `git restore index.js`
- staged 되지 않은 상태에서, 커밋이력으로 롤백하고 싶을 때
- 원래 git checkout 명령어였는데 깃 버전 업데이트하면서 restore로 바뀜. 브랜치 바꿀때 사용하는 명령어랑 똑같아서 헷갈렸음.
### `git restore --staged index.js`
- staged된(add를 했음) 파일을 다시 내리고 싶을 때

## remote
- `git remote add origin https://github.com/seyoungjoy/git.git` : 원격 저장소의 주소 설정
- `git remote get-url origin` : 원격 저장소 주소 확인

## push
- `git push origin master` : 원격 저장소 master에 업로드하겠다.

## pull
- `git pull origin master` : 원격 저장소 master에 있는 소스들을 업데이트하겠다.

## reset
- commit 취소 : 실수로 커밋했을 때 사용.
  HEAD : 현재 위치
- `git reset HEAD~1` : commit 내역 한단계 되돌아감.
- 실수했던 커밋 자체를 없애버림.
`git reset HEAD~1 --soft` : 커밋 취소 후 staged로
`git reset HEAD~1 --mixed` : 기본, 커밋 취소 후 unstaged로
`git reset --hard HEAD~1` : 저장된 커밋들 중 하나로 헤드를 이동하는 작업.
만약 reset을 실수로 했다면 git reflog를 통해 과거의 커밋내력을 보고 해당 로그로
`git reset --hard <돌아갈 커밋로그>`

## git commit 내역 삭제
1. git commit 내역 확인
```
git log
```

2. commit 내역 삭제
```
git reset HEAD~숫자 // 삭제하고싶은 커밋 개수
git log // 삭제 되었는지 확인
```

3. remote에 삭제한 커밋 내역 push
- 커밋 히스토리를 강제로 push하기 때문에 `--force` or `-f` 명령어 추가.

```
git push -f origin [branch name]
```

❗ 내가 커밋한 내용을 다른 사람이 pull 받았으면 삭제한 커밋 내역 적용안됨.
