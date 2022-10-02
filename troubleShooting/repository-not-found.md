## Issue
  - 회사 프로젝트 레포를 집에서 작업하려고 git clone을 했더니 레포를 찾을 수 없다고 나온다.
```
remote: Repository not found.
```

## Cause
- 내 컴퓨터에는 회사 계정이 아닌 개인 계정의 key chain이 등록되어 있어서 레포를 못찾고 있는 것.

## TroubleShooting
- git clone을 할 때 해당 계정의 토큰을 함께 넣어 해결할 수 있었다.
```
git clone https://[git user name]:[git password]@[git repository address]
```

## Reference
- https://velog.io/@devmin/git-repository-multi-account