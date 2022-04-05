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
