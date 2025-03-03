# Git BAsics Exercises
## Bundle 1
### Ex 1
```bash

Kubahos-iMac-2:git-challenge gymkubaho$ git status
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        file1.txt
        scr/

nothing added to commit but untracked files present (use "git add" to track)


gymkubaho@Kubahos-iMac-2 git-challenge % git  branch -d test
Deleted branch test (was ef43277).
gymkubaho@Kubahos-iMac-2 git-challenge % git checkout -b dev

Switched to a new branch 'dev'
gymkubaho@Kubahos-iMac-2 git-challenge % git checkout -b test

Switched to a new branch 'test'
gymkubaho@Kubahos-iMac-2 git-challenge % git switch  dev
Switched to branch 'dev'
gymkubaho@Kubahos-iMac-2 git-challenge %  git branch -d test
Deleted branch test (was ef43277).
gymkubaho@Kubahos-iMac-2 git-challenge % git   branch
* dev
  main
gymkubaho@Kubahos-iMac-2 git-challenge % 
```

### Ex 1
```bash
gymkubaho@Kubahos-iMac-2 git-challenge % echo "<h1>Home Page</h1>" > home.html
gymkubaho@Kubahos-iMac-2 git-challenge % git add home.html
gymkubaho@Kubahos-iMac-2 git-challenge % git stash push -m "Stashing home.html"
Saved working directory and index state On dev: Stashing home.html
gymkubaho@Kubahos-iMac-2 git-challenge % echo "<h1>About Us</h1>" > about.html
gymkubaho@Kubahos-iMac-2 git-challenge % git add about.html
gymkubaho@Kubahos-iMac-2 git-challenge % git stash push -m "Stashing about.html"
Saved working directory and index state On dev: Stashing about.html
gymkubaho@Kubahos-iMac-2 git-challenge % echo "<h1>Our Team</h1>" > team.html

gymkubaho@Kubahos-iMac-2 git-challenge % git add team.html
gymkubaho@Kubahos-iMac-2 git-challenge % git stash push -m "Stashing team.html"
Saved working directory and index state On dev: Stashing team.html
gymkubaho@Kubahos-iMac-2 git-challenge % git stash pop
On branch dev
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   team.html

Dropped refs/stash@{0} (eeba257981ac948e9042833f812e2e11bdf7869e)
gymkubaho@Kubahos-iMac-2 git-challenge % git stash list

stash@{0}: On dev: Stashing about.html
stash@{1}: On dev: Stashing home.html
gymkubaho@Kubahos-iMac-2 git-challenge % git stash pop stash@{1}
On branch dev
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   home.html
        new file:   team.html

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   scr/README.md

Dropped stash@{1} (4097db852e0e9f931a5b2c1406f07a865f8acbc7)
gymkubaho@Kubahos-iMac-2 git-challenge % git add home.html about.html
fatal: pathspec 'about.html' did not match any files
gymkubaho@Kubahos-iMac-2 git-challenge % git commit -m "Restored home.html and about.html from stash"
[dev 6934650] Restored home.html and about.html from stash
 2 files changed, 2 insertions(+)
 create mode 100644 home.html
 create mode 100644 team.html
gymkubaho@Kubahos-iMac-2 git-challenge % git push origin dev
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (4/4), 404 bytes | 404.00 KiB/s, done.
Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
remote: 
remote: Create a pull request for 'dev' on GitHub by visiting:
remote:      https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES/pull/new/dev
remote: 
To https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES.git
 * [new branch]      dev -> dev
gymkubaho@Kubahos-iMac-2 git-challenge % git stash list

stash@{0}: On dev: Stashing about.html
gymkubaho@Kubahos-iMac-2 git-challenge % git stash pop stash@{0}
On branch dev
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   about.html

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   scr/README.md

Dropped stash@{0} (7a7bae13d71cc699da443994de81ccea69bcb04c)
gymkubaho@Kubahos-iMac-2 git-challenge % git reset HEAD team.html
Unstaged changes after reset:
M       scr/README.md
gymkubaho@Kubahos-iMac-2 git-challenge % rm team.html 
gymkubaho@Kubahos-iMac-2 git-challenge % git status
On branch dev
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   about.html

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   scr/README.md
        deleted:    team.html

gymkubaho@Kubahos-iMac-2 git-challenge % git commit -m "Removed team.html"
[dev 41ca032] Removed team.html
 1 file changed, 1 insertion(+)
 create mode 100644 about.html
gymkubaho@Kubahos-iMac-2 git-challenge % git push origin dev
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 295 bytes | 295.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES.git
   6934650..41ca032  dev -> dev
gymkubaho@Kubahos-iMac-2 git-challenge % 
```