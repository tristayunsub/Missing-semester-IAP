$ ls .git


HEAD  config  description  hooks/  info/  objects/  refs/

git help init

git status 

On branch master

No commits yet

echo " hello world" > hello.txt

 git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        hello.txt

  
  git add hello.txt -> changes to be committed
 
  
  git commit
  [master (root-commit) 8ac73ef] Add hello.txt
  1 file changed, 1 insertion(+)
 create mode 100644 hello.txt
  
 what is 8ac73ef?
  its a sha-1 hash 
  
  git log 
commit 8ac73ef033232bdeb3cce5f52f5daf3e6cf8d5fd (HEAD->master)
  
  git cat-file -p 8ac73ef
  tree ca3726939b8ddb131a3679ab28453659aac6a960
  author YUNSEOPLIM <tristayunsub@gmail.com> 1649138529 +0900
  committer YUNSEOPLIM <tristayunsub@gmail.com> 1649138529 +0900
 
  git cat-file -p ca3726939b8ddb131a3679ab28453659aac6a960
  100644 blob 9409bd50fd6569a1a509ea54b73b5e39ff32cee2    hello.txt
  
  git cat-file -p  9409bd50fd6569a1a509ea54b73b5e39ff32cee2
   hello world

  ```
incredibly helpful command
 
  git log --all --graph --decorate
```
 * commit 8ac73ef033232bdeb3cce5f52f5daf3e6cf8d5fd (HEAD -> master)
  Author: YUNSEOPLIM <tristayunsub@gmail.com>
  Date:   Tue Apr 5 15:02:09 2022 +0900

      Add hello.txt
 
  
  echo "another line" >> hello.txt
  cat hello.txt
  
   hello world
   another line
  
  git commit but i still didnt git add
  git add hello.txt
  
  and then we do   git log --all --graph --decorate again

  ```
  * commit 4f78b03b87fed125a5dedd75e4da33a0cfc09a9b (HEAD -> master)
| Author: YUNSEOPLIM <tristayunsub@gmail.com>
| Date:   Tue Apr 5 15:17:32 2022 +0900
|
|     asd
|
* commit 8ac73ef033232bdeb3cce5f52f5daf3e6cf8d5fd
  Author: YUNSEOPLIM <tristayunsub@gmail.com>
  Date:   Tue Apr 5 15:02:09 2022 +0900

      Add hello.txt
  ```
  
  ```
  git checkout 8ac73ef
  ```
  Note: switching to '8ac73ef'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

HEAD is now at 8ac73ef Add hello.txt

  ```
  $ git log --all --graph --decorate
* commit 4f78b03b87fed125a5dedd75e4da33a0cfc09a9b (master)
| Author: YUNSEOPLIM <tristayunsub@gmail.com>
| Date:   Tue Apr 5 15:17:32 2022 +0900
|
|     asd
|
* commit 8ac73ef033232bdeb3cce5f52f5daf3e6cf8d5fd (HEAD)
  Author: YUNSEOPLIM <tristayunsub@gmail.com>
  Date:   Tue Apr 5 15:02:09 2022 +0900

      Add hello.txt

  HEAD IS Changed!
 ```
 
  in orderto go back to 4f78~blahblah 
  
  git checkout master
  
  
  git diff hello.txt > respecct to HEAD 
  or git diff 8ac73ef hello.txt
  
  diff --git a/hello.txt b/hello.txt
  index 9409bd5..fe37475 100644
  --- a/hello.txt
  +++ b/hello.txt
  @@ -1 +1,4 @@
  - hello world
  +hello world
  +another line
  +sasfsfw
  
  you can do git diff HEAD hello.txt
  
  HEAD refers to last snapshot. 
  
  ```
  git diff 8ac73ef HEAD hello.txt 
  means what changed 8ac73ef to HEAD
  ```
  diff --git a/hello.txt b/hello.txt
index 9409bd5..1bc2148 100644
--- a/hello.txt
+++ b/hello.txt
@@ -1 +1,2 @@
  hello world
  +another line

  
  vim animal.py
  
  python animal.py
  hello
  
  Untracked files:
  (use "git add <file>..." to include in what will be committed)
        animal.py

  git add animal.py
  
  * commit caded3788f2830d6d96cc90dc1bafbfb4f6365ae (HEAD -> master)
| Author: YUNSEOPLIM <tristayunsub@gmail.com>
| Date:   Tue Apr 5 15:37:45 2022 +0900
|
|     Add animal.py

  
  
  how to manage git branch
   
  
  git branch -vv 
  * master caded37 Add animal.py
  git branch cat
  
  git log --all --graph --decorate
* commit caded3788f2830d6d96cc90dc1bafbfb4f6365ae (HEAD -> master, cat)
| Author: YUNSEOPLIM <tristayunsub@gmail.com>
| Date:   Tue Apr 5 15:37:45 2022 +0900
|
|     Add animal.py
  
  git diff
  
  shows us chaneged line
 
  $ git commit

 [cat 666a2c2] Add cat functionalitty
 1 file changed, 7 insertions(+)

 
 git log --all --graph --decorate --oneline
 
 
 * 666a2c2 (HEAD -> cat) Add cat functionalitty
* caded37 (master) Add animal.py
* 4f78b03 asd
* 8ac73ef Add hello.txt
  
  git checkout master
  
  cat animal.py
  
  import sys

def default():
    print('Hello')

def main():
    default()

if __name__ == '__main__':
    main()

  ```
  git log --all --graph --decorate --oneline
* 666a2c2 (cat) Add cat functionalitty
* caded37 (***HEAD -> master***) Add animal.py
* 4f78b03 asd
* 8ac73ef Add hello.txt
  
 
  git branch dog; git checkout dog

  $ git log --all --graph --decorate --oneline
* 666a2c2 (cat) Add cat functionalitty
* caded37 (***HEAD -> dog, master***) Add animal.py
* 4f78b03 asd
* 8ac73ef Add hello.txt
  ```
  
  
  so git diff function shows you changed line
 
 $ git log --all --graph --decorate --oneline
 
 ```
* ca9e802 (HEAD -> dog) add dog functionality
| * 666a2c2 (cat) Add cat functionalitty
|/
* caded37 (master) Add animal.py
* 4f78b03 asd
* 8ac73ef Add hello.txt
```
 
 git branch and git merge
 
 i wanna merge cat functionality and dog functionality into master
 
 Fast-forward
what fast-forward mean?

 
 
Auto-merging animal.py
CONFLICT (content): Merge conflict in animal.py
 
``` 
def main():
<<<<<<< HEAD
    if sys.argv[1] ==  'cat':
        cat()
    else:
        default()

    default()
=======          /conflict marker you should delete them
    if sys.argv[1] == 'dog':
        dog()
    else:
         default()
>>>>>>> dog

if __name__ == '__main__':
    main()
```
to
 ```
def main():

    if sys.argv[1] ==  'cat':
        cat()


    elif sys.argv[1] == 'dog':
        dog()
    else:
         default()

```
 
 like this^
 
 git merge --continue
error: Committing is not possible because you have unmerged files.
hint: Fix them up in the work tree, and then use 'git add/rm <file>'
hint: as appropriate to mark resolution and make a commit.
fatal: Exiting because of an unresolved conflict.
 
 
 $ git merge --continue
[master bde6558] Merge branch 'dog'
 
 
``` 
 bde6558 (HEAD -> master) Merge branch 'dog'
|\
| * ca9e802 (dog) add dog functionality
* | 666a2c2 (cat) Add cat functionalitty
```
 
 mkdir remote
 
 cd remote
 
 ```
 git init --bare
Initialized empty Git repository in C:/Users/엘리트북/demo/remote/
```
 
 
git remote add origin
 
 
 or git remote add <name> <url>
 
 
 git remote add origin /remote

 git push <remote> <local branch>:<remote branch>
 
 git push origin master:master
 
 (HEAD -> master, origin/master) merge branch
 
 git add animal.py
 git commit -m 'x'
 
 (HEAD -> master) X
 (origin/master) merge branch'dog'
 
 git clone remote demo2
 Cloning into 'demo2'...
warning: You appear to have cloned an empty repository.
done.

 cd demo2

 ```
 git branch --set-upstream-to=origin/master
 
 means Branch 'master' set up to track branch 'master' from 'origin'
 ```
 
 
git branch -vv 


 
git fetch 
 
 
 git fetch; git merge
 
 
 git pull
 
 
 fast-forward 
 
 
 ```
 git remote 
 
 sending your changes into remote from your local machine
 ```
 
 
 git config
 
 vim ~/.gitconfig
 
 
 
 git bisect?
 
 7.10 Git 도구 - Git으로 버그 찾기
 git blame 과 git bisect
 https://git-scm.com/book/ko/v2/Git-%EB%8F%84%EA%B5%AC-Git%EC%9C%BC%EB%A1%9C-%EB%B2%84%EA%B7%B8-%EC%B0%BE%EA%B8%B0

 버그를 찾을 때 먼저 그 코드가 왜, 언제 추가했는지 알고 싶을 것이다. 이때는 파일 어노테이션을 활용한다. 한 줄 한 줄 마지막으로 커밋한 사람이 누구인지, 언제 마지막으로 커밋했는지 볼 수 있다. 어떤 메소드에 버그가 있으면 git blame 명령으로 그 메소드의 각 라인을 누가 언제 마지막으로 고쳤는지 찾아낼 수 있다.
 
 
 git blame 명령을 사용하여 어떤 커밋이나 커밋 저자가 리눅스 커널의 Makefile 각 라인을 수정했는지 확인해보고자 한다. -L 옵션을 사용하여 전체 파일이 아니라 69 라인부터 82 라인까지 제한하여 부분적으로 확인할 수도 있다.

git blame -L 1,10 animal.py
 
 
 이진 탐색
파일 어노테이션은 특정 이슈와 관련된 커밋을 찾는 데에도 좋다. 문제가 생겼을 때 의심스러운 커밋이 수십, 수백 개에 이르는 경우 도대체 어디서부터 시작해야 할지 모를 수 있다. 이때는 git bisect 명령이 유용하다. bisect 명령은 커밋 히스토리를 이진 탐색 방법으로 좁혀 주기 때문에 이슈와 관련된 커밋을 최대한 빠르게 찾아낼 수 있도록 도와준다.

코드를 운용 환경에 배포하고 난 후에 개발할 때 발견하지 못한 버그가 있다고 보고받았다. 그런데 왜 그런 현상이 발생하는지 아직 이해하지 못하는 상황을 가정해보자. 해당 이슈를 다시 만들고 작업하기 시작했는데 뭐가 잘못됐는지 알아낼 수 없다. 이럴 때 bisect 명령을 사용하여 코드를 뒤져 보는 게 좋다. 먼저 git bisect start 명령으로 이진 탐색을 시작하고 git bisect bad 를 실행하여 현재 커밋에 문제가 있다고 표시를 남기고 나서 문제가 없는 마지막 커밋을 git bisect good <good_commit> 명령으로 표시한다.
  
  
 git bisect start, bad, good 
 
 수백 개의 커밋들 중에서 버그가 만들어진 커밋을 찾는 데 몇 분밖에 걸리지 않는다. 프로젝트가 정상적으로 수행되면 0을 반환하고 문제가 있으면 1을 반환하는 스크립트를 만든다면, 이 git bisect 과정을 완전히 자동으로 수행할 수 있다. 먼저 bisect start 명령으로 이진 탐색에 사용할 범위를 알려준다. 위에서 한 것처럼 문제가 있다고 아는 커밋과 문제가 없다고 아는 커밋을 넘기면 된다.

 ```
$ git bisect start HEAD v1.0
$ git bisect run test-error.sh
 ```
 
 
 
 thank you
  
  
31:42    git add . , git commit -m <msg> , git log , git cat-file -p <8d-commit-hash/ branch-hash/ file-hash>

32:47    git commit -a , git add :/

35:23    git log --all --graph --decorate
  

  36:12    git status (have staged or commited or not)

  41:41    git-checkout -f <8d-commit-hash / 8d-branch-hash>  (switch branch)

  43:11    git diff hello.txt (show the changes in the file compared to the last commit)

  43:28    git diff <8d-commit-hash> hello.txt (compared to the branch)

  44:33    git diff HEAD hello.txt

  46:22    git diff <8d-commit-hash) HEAD hello.txt (change from to)

    50:06    git branch (print all the branches) , git branch -vv (extra verbose)

   50:17    git branch cat (create new branch that points to the HEAD you are currently looking) , git checkout cat

      53:56    git branch -b dog
52:53    git log --all --graph --decorate --oneline (more compact view)

56:27    git merge cat (can do cat dog) 
                                     
                                     
58:51    git merge --abort
                                     
                                     
1:00:41    git add . , git merge --continue > git commit -m <msg> / git commit
  
  
59:37    <<<<< HEAD points to last snapshot in master branch, >>>> dog points to the branch you're trying to merge.


  1:04:17    git init --bare (initiatialize empty git repo in current dir), 

  1:04:20    git remote add <remote name> <remote repository URL>,  git push <remote name> <local branch>: <remote branch>

  1:07:54    git clone <url> <folder name>

  1:10:33    git branch --set-upstream-to=origin/master


  1:18:12    git blame .config.yml (who edit the file on which commit message by who, when) , git show <commit hash> (to get line changes like git diff)

  
  
1:19:22    git stash (changes saved somewhere) , git stash pop (get saved back)
  

1:20:46    git bisect
  
  
1:21:48    git ignore (put file name or *.extension)

  
  
***System Design***
