# 1/15 Quiz

## 1.
### 다음 명령어에 대해  간단히 설명하세요.

### git init

주어진 directory를 git 저장소로 만든다. stage와 local repository가 .git 내에 생성된다. 

### git clone

remote repository를 local에 복사한다. 즉 working tree를 만들고 checkout을 한다. 

### git add

working tree에 있는 작업을 stage에 올린다. 

### git commit

stage에 올려져 있는 작업으로 commit 객체를 만들고 이를 local repository에 저장한다. commit을 하는 순간 HEAD는 새로운 commit을 향한다. (HEAD: 새로운 commit의 부모 commit을 가리킴) 

### git push 

local repository에 있는 작업(commit, HEAD, branch 정보 등)을 remote repository에 저장한다.

### git fetch

remote repository에 있는 작업을 local repository로 가져온다. 

### git pull

fetch + merge 로 이루어져 있다. remote repository에 있는 작업을 local repository로 가져온 다음 working tree와 stage를 origin의 HEAD와 merge 시킨다. 

### git checkout

현재 HEAD를 해당 branch로 이동한다. working directory와 stage를 해당 commit과 같도록 한다. 

### git merge

두 branch를 합쳐서 새로운 commit으로 만들고 HEAD를 새로 만들어진 commit으로 옮긴다. 

### git rebase

checkout한 branch를 타겟 branch에 붙인 다음 새로운 commit을 생성한다. 이때 checkout한 branch는 사라지고 하나의 branch만 남는다. 

### git reset

HEAD를 해당 commit으로 향하게 한다. 이때 해당 commit의 자식들을 가리킬 방법이 없으면 자식들에게 접근 할 수 없게 된다. 


## 2.
### a.txt b.txt c.txt 세 개의 파일이 있다. 내용을 모두 같고, 각각 다른 디렉토리에 저장되어 있다. 또한 다른 커밋 3곳에 흩어져서 커밋되어 있다.  각 파일의 용량이 100바이트라고 하면 이 파일 세개를 저장하기 위해 필요한 전체 용량은 얼마인가?

64 bit ISA 기준
300B(file 크기) + 24B(HEAD) = 324B

정답
commit을 할 때 파일에 대한 SHA-1 checksum을 비교해 동일한 hash 값이면 추가적인 blob을 만들지 않는다. 

## 3. 
### 레오나의 저장소에는 C1 <- C2 <- C3 새 개의 커밋이 있다. 그런데 C2와 C3의 커밋의 순서를 바꾸고 싶다. 가능한 짧은 명령으로 해결해 보자.

정답
git reset --hard HEAD~2
git reflog 
git reset --hard (checksum of C3)

or

git rebase -i

## 4. 
### 한조는 브랜치를 좋아해서 브랜치를 1000개 만들었다. 이 때 저장소의 전체 용량은 얼마 증가할까?

64 bit ISA 기준
1000 * 8B(bracnh ref)  = 8KB

정답
branch 하나 당 40B checksum 만 생성된다. 
따라서 1000*40B = 40KB
