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
