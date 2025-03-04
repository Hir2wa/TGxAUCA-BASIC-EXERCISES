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

## Bundle 2

### Ex 1

```bash
gymkubaho@Kubahos-iMac-2 git-challenge % git checkout -b ft/bundle-2
Switched to a new branch 'ft/bundle-2'
gymkubaho@Kubahos-iMac-2 git-challenge % echo "<h1>Our Services</h1>" > services.html
gymkubaho@Kubahos-iMac-2 git-challenge % git add services.html
gymkubaho@Kubahos-iMac-2 git-challenge % git commit -m "Added services.html page"
[ft/bundle-2 a99707f] Added services.html page
 1 file changed, 1 insertion(+)
 create mode 100644 services.html
gymkubaho@Kubahos-iMac-2 git-challenge % git push -u origin ft/bundle-2

Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 343 bytes | 343.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote:
remote: Create a pull request for 'ft/bundle-2' on GitHub by visiting:
remote:      https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES/pull/new/ft/bundle-2
remote:
To https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES.git
 * [new branch]      ft/bundle-2 -> ft/bundle-2
branch 'ft/bundle-2' set up to track 'origin/ft/bundle-2'.
gymkubaho@Kubahos-iMac-2 git-challenge % git switch main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
gymkubaho@Kubahos-iMac-2 git-challenge %
```

### Ex 2

```bash
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES>  git branch
  dev
  ft/bundle-2
* main
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git checkout -b ft/service-redesign
Switched to a new branch 'ft/service-redesign'
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git add services.html
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git commit -m "Updated service.html with redesign changes"
[ft/service-redesign 8e935c6] Updated service.html with redesign changes
 1 file changed, 11 insertions(+), 1 deletion(-)
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git push origin ft/service-redesign
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 12 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 501 bytes | 501.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
remote:
remote: Create a pull request for 'ft/service-redesign' on GitHub by visiting:
remote:      https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES/pull/new/ft/service-redesign
remote:
To https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES.git
 * [new branch]      ft/service-redesign -> ft/service-redesign
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES>
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git  switch main
Switched to branch 'main'
Your branch is behind 'origin/main' by 2 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)
remote: Create a pull request for 'ft/service-redesign' on GitHub by visiting:
remote:      https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES/pull/new/ft/service-redesign
remote:
To https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES.git
 * [new branch]      ft/service-redesign -> ft/service-redesign
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES>
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git  switch main
Switched to branch 'main'
Your branch is behind 'origin/main' by 2 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)
remote:      https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES/pull/new/ft/service-redesign
remote:
To https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES.git
 * [new branch]      ft/service-redesign -> ft/service-redesign
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES>
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git  switch main
Switched to branch 'main'
Your branch is behind 'origin/main' by 2 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)
remote:
To https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES.git
 * [new branch]      ft/service-redesign -> ft/service-redesign
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES>
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git  switch main
Switched to branch 'main'
Your branch is behind 'origin/main' by 2 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)
To https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES.git
 * [new branch]      ft/service-redesign -> ft/service-redesign
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES>
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git  switch main
Switched to branch 'main'
Your branch is behind 'origin/main' by 2 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES>
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git  switch main
Switched to branch 'main'
Your branch is behind 'origin/main' by 2 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git pull origin main
Switched to branch 'main'
Your branch is behind 'origin/main' by 2 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git pull origin main
From https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES
Your branch is behind 'origin/main' by 2 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git pull origin main
From https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES
 * branch            main       -> FETCH_HEAD
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git pull origin main
From https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES
 * branch            main       -> FETCH_HEAD
Updating a879bd8..76b23ee
From https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES
 * branch            main       -> FETCH_HEAD
Updating a879bd8..76b23ee
 * branch            main       -> FETCH_HEAD
Updating a879bd8..76b23ee
Updating a879bd8..76b23ee
Fast-forward
 services.html | 12 +++++++++++-
 services.html | 12 +++++++++++-
 1 file changed, 11 insertions(+), 1 deletion(-)

// i have merged remotely


```

## Bundle 3

### Ex 1

```bash
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git branch
  dev
  ft/bundle-2
  ft/service-redesign
* main
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git checkout -b ft/team-page
Switched to a new branch 'ft/team-page'
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git add team.html
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git commit -m "Add team page with team members"
[ft/team-page cc7dc30] Add team page with team members
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 team.html
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git push origin ft/team-page
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 12 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 284 bytes | 284.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/team-page' on GitHub by visiting:
remote:      https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES/pull/new/ft/team-page
remote:
To https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES.git
 * [new branch]      ft/team-page -> ft/team-page
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git switch main
Switched to branch 'main'
Your branch is behind 'origin/main' by 2 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git branch
  dev
  ft/bundle-2
  ft/service-redesign
  ft/team-page
* main
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git checkout -b ft/contact-page
Switched to a new branch 'ft/contact-page'
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git checkout ft/team-page
Switched to branch 'ft/team-page'
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git log --oneline
cc7dc30 (HEAD -> ft/team-page, origin/ft/team-page) Add team page with team members
bf5f679 (main, ft/contact-page) updated README.md for  Bundle2
76b23ee Merge pull request #2 from Hir2wa/ft/service-redesign
8e935c6 (origin/ft/service-redesign, ft/service-redesign) Updated service.html with redesign changes
a879bd8 Merge branch 'main' of https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES
e3579e8 updated README.md
eff892f Updated README.md
bc515c0 Merge pull request #1 from Hir2wa/ft/bundle-2
a99707f (origin/ft/bundle-2, ft/bundle-2) Added services.html page
7da3bf1 Updated README.md
ef43277 Initial commit with project setup
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git checkout ft/contact-page
Switched to branch 'ft/contact-page'
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git cherry-pick cc7dc30
[ft/contact-page c9c5733] Add team page with team members
 Date: Mon Mar 3 12:47:26 2025 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 team.html
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git add contact.html
fatal: pathspec 'contact.html' did not match any files
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git add contact.html
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git commit -m "Add contact page"
[ft/contact-page 37d7698] Add contact page
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 contact.html
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git push origin ft/contact-page
Enumerating objects: 6, done.
Counting objects: 100% (6/6), done.
Delta compression using up to 12 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (5/5), 548 bytes | 78.00 KiB/s, done.
Total 5 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), done.
remote:
remote: Create a pull request for 'ft/contact-page' on GitHub by visiting:
remote:      https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES/pull/new/ft/contact-page
remote:
To https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES.git
 * [new branch]      ft/contact-page -> ft/contact-page
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git branch
  dev
  ft/bundle-2
* ft/contact-page
  ft/service-redesign
  ft/team-page
Revert "Add team page with team members"
Revert "Add team page with team members"
Revert "Add team page with team members"
This reverts commit cc7dc309680fd467cf10e9f8965e6417c00d3bc1.
  main
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git checkout -b ft/faq-page
Switched to a new branch 'ft/faq-page'
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git commit -m "Add FAQ page"
On branch ft/faq-page
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        faq.html

nothing added to commit but untracked files present (use "git add" to track)
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git  add .
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git commit -m "Add FAQ page"
[ft/faq-page 762f2da] Add FAQ page
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 faq.html
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git push origin ft/faq-page
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 12 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 236 bytes | 236.00 KiB/s, done.
Total 2 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/faq-page' on GitHub by visiting:
remote:      https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES/pull/new/ft/faq-page
Counting objects: 100% (3/3), done.
Delta compression using up to 12 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 236 bytes | 236.00 KiB/s, done.
Total 2 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/faq-page' on GitHub by visiting:
remote:      https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES/pull/new/ft/faq-page
remote:
Delta compression using up to 12 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 236 bytes | 236.00 KiB/s, done.
Total 2 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/faq-page' on GitHub by visiting:
remote:      https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES/pull/new/ft/faq-page
remote:
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 236 bytes | 236.00 KiB/s, done.
Total 2 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/faq-page' on GitHub by visiting:
remote:      https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES/pull/new/ft/faq-page
remote:
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/faq-page' on GitHub by visiting:
remote:      https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES/pull/new/ft/faq-page
remote:
remote:
remote: Create a pull request for 'ft/faq-page' on GitHub by visiting:
remote:      https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES/pull/new/ft/faq-page
remote:
remote: Create a pull request for 'ft/faq-page' on GitHub by visiting:
remote:      https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES/pull/new/ft/faq-page
remote:
To https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES.git
 * [new branch]      ft/faq-page -> ft/faq-page
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git revert cc7dc30
[ft/faq-page fa4a782] This reverts commit cc7dc309680fd467cf10e9f8965e6417c00d3bc1.
remote:
To https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES.git
 * [new branch]      ft/faq-page -> ft/faq-page
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git revert cc7dc30
[ft/faq-page fa4a782] This reverts commit cc7dc309680fd467cf10e9f8965e6417c00d3bc1.
 1 file changed, 0 insertions(+), 0 deletions(-)
To https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES.git
 * [new branch]      ft/faq-page -> ft/faq-page
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git revert cc7dc30
[ft/faq-page fa4a782] This reverts commit cc7dc309680fd467cf10e9f8965e6417c00d3bc1.
 1 file changed, 0 insertions(+), 0 deletions(-)
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git revert cc7dc30
[ft/faq-page fa4a782] This reverts commit cc7dc309680fd467cf10e9f8965e6417c00d3bc1.
 1 file changed, 0 insertions(+), 0 deletions(-)
 delete mode 100644 team.html
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git push origin ft/faq-page
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
 delete mode 100644 team.html
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git push origin ft/faq-page
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 12 threads
Compressing objects: 100% (2/2), done.
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 12 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 255 bytes | 255.00 KiB/s, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 12 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 255 bytes | 255.00 KiB/s, done.
Total 2 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
Delta compression using up to 12 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 255 bytes | 255.00 KiB/s, done.
Total 2 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
Writing objects: 100% (2/2), 255 bytes | 255.00 KiB/s, done.
Total 2 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES.git
   762f2da..fa4a782  ft/faq-page -> ft/faq-page
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES.git
   762f2da..fa4a782  ft/faq-page -> ft/faq-page
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git  switch main
Switched to branch 'main'
Your branch is behind 'origin/main' by 5 commits, and can be fast-forwarded.
Your branch is behind 'origin/main' by 5 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git pull origin main
From https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES
 * branch            main       -> FETCH_HEAD
Updating bf5f679..de35ff6
Fast-forward
 contact.html | 0
 team.html    | 0
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 contact.html
 create mode 100644 team.html
```

### Ex 2:

```bash
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git branch
  dev
  ft/bundle-2
  ft/contact-page
* ft/faq-page
  ft/service-redesign
  ft/team-page
  main
  r
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git checkout -b ft/home-page-redesign
Switched to a new branch 'ft/home-page-redesign'
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git switch main
M       src/README.md
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git  add src/
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git commit -m "Updated main branch with new changes"
[main df60250] Updated main branch with new changes
 1 file changed, 253 insertions(+)
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git push origin main
Enumerating objects: 9, done.
Counting objects: 100% (9/9), done.
Delta compression using up to 12 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (6/6), 2.02 KiB | 413.00 KiB/s, done.
Total 6 (delta 3), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (3/3), completed with 2 local objects.
To https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES.git
   de35ff6..df60250  main -> main
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git checkout ft/home-page-redesign
Switched to branch 'ft/home-page-redesign'
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git rebase main
warning: skipped previously applied commit fa4a782
hint: use --reapply-cherry-picks to include skipped commits
hint: Disable this message with "git config advice.skippedCherryPicks false"
Successfully rebased and updated refs/heads/ft/home-page-redesign.
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git add .
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git rebase --continue
fatal: no rebase in progress
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git add .
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git commit -m "Redesigned  contact  page"
[ft/home-page-redesign 3cc1331] Redesigned  contact  page
 2 files changed, 18 insertions(+)
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git push origin ft/home-page-redesign
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 12 threads
Compressing objects: 100% (5/5), done.
Writing objects: 100% (5/5), 717 bytes | 239.00 KiB/s, done.
Total 5 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
Total 5 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/home-page-redesign' on GitHub by visiting:
remote:      https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES/pull/new/ft/home-page-redesign
remote:
To https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES.git
 * [new branch]      ft/home-page-redesign -> ft/home-page-redesign
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git switch main
Switched to branch 'main'
Your branch is behind 'origin/main' by 3 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)
Total 5 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/home-page-redesign' on GitHub by visiting:
remote:      https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES/pull/new/ft/home-page-redesign
remote:
To https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES.git
 * [new branch]      ft/home-page-redesign -> ft/home-page-redesign
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git switch main
Switched to branch 'main'
Your branch is behind 'origin/main' by 3 commits, and can be fast-forwarded.
Total 5 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/home-page-redesign' on GitHub by visiting:
remote:      https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES/pull/new/ft/home-page-redesign
remote:
To https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES.git
Total 5 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/home-page-redesign' on GitHub by visiting:
remote:      https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES/pull/new/ft/home-page-redesign
remote:
Total 5 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/home-page-redesign' on GitHub by visiting:
remote:      https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES/pull/new/ft/home-page-redesign
Total 5 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'ft/home-page-redesign' on GitHub by visiting:
remote:      https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES/pull/new/ft/home-page-redesign
remote:
To https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES.git
 * [new branch]      ft/home-page-redesign -> ft/home-page-redesign
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git switch main
Switched to branch 'main'
Your branch is behind 'origin/main' by 3 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES>



```

## Bundle 4:

### Ex 2:

```bash
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git remote add git-copy https://github.com/Hir2wa/TGxAUCA-BASIC_EXERCISE_COPY.git
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git remote -v
git-copy        https://github.com/Hir2wa/TGxAUCA-BASIC_EXERCISE_COPY.git (fetch)
git-copy        https://github.com/Hir2wa/TGxAUCA-BASIC_EXERCISE_COPY.git (push)
origin  https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES.git (fetch)
origin  https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES.git (push)
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES>
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git add src/
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git commit -m "Updated README.md"
[main 9e1382b] Updated README.md
 1 file changed, 14 insertions(+)
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git push origin main
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 12 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (4/4), 500 bytes | 500.00 KiB/s, done.
Total 4 (delta 3), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (3/3), completed with 3 local objects.
To https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES.git
   f8f8d48..9e1382b  main -> main
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git push git-copy main
Enumerating objects: 68, done.
Counting objects: 100% (68/68), done.
Delta compression using up to 12 threads
Compressing objects: 100% (59/59), done.
Writing objects: 100% (68/68), 14.93 KiB | 849.00 KiB/s, done.
Total 68 (delta 24), reused 21 (delta 5), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (24/24), done.
To https://github.com/Hir2wa/TGxAUCA-BASIC_EXERCISE_COPY.git
 * [new branch]      main -> main
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git checkout -b ft/footer
Switched to a new branch 'ft/footer'
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git add src/
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git commit -m "added footer and updated README.md"
[ft/footer 5834787] added footer and updated README.md
 2 files changed, 30 insertions(+)
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git add src/
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git commit -m "updated index.html bu adding p"
[ft/footer c5ad151] updated index.html bu adding p
 1 file changed, 1 insertion(+), 1 deletion(-)
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git push origin ft/footer
Enumerating objects: 13, done.
Counting objects: 100% (13/13), done.
Delta compression using up to 12 threads
Compressing objects: 100% (9/9), done.
Writing objects: 100% (9/9), 1.14 KiB | 585.00 KiB/s, done.
Total 9 (delta 6), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (6/6), completed with 3 local objects.
remote:
remote: Create a pull request for 'ft/footer' on GitHub by visiting:
remote:      https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES/pull/new/ft/footer
remote:
To https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES.git
 * [new branch]      ft/footer -> ft/footer
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES>
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git branch
  dev
  ft/bundle-2
  ft/contact-page
  ft/faq-page
* ft/footer
  ft/home-page-redesign
  ft/service-redesign
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git switch main
Switched to branch 'main'
Your branch is behind 'origin/main' by 3 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git checkout -b ft/squashing
Switched to a new branch 'ft/squashing'
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git merge --squash ft/footer
Updating 9e1382b..c5ad151
Fast-forward
Squash commit -- not updating HEAD
 src/README.md  | 26 ++++++++++++++++++++++++++
 src/index.html |  4 ++++
 2 files changed, 30 insertions(+)
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git commit -m "footer changes squashing"
[ft/squashing f7a3b4b] footer changes squashing
 2 files changed, 30 insertions(+)
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git push origin ft/squashing
Enumerating objects: 9, done.
Counting objects: 100% (9/9), done.
Delta compression using up to 12 threads
Compressing objects: 100% (5/5), done.
Writing objects: 100% (5/5), 868 bytes | 868.00 KiB/s, done.
Total 5 (delta 3), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (3/3), completed with 3 local objects.
remote:
remote: Create a pull request for 'ft/squashing' on GitHub by visiting:
remote:      https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES/pull/new/ft/squashing
remote:
To https://github.com/Hir2wa/TGxAUCA-BASIC-EXERCISES.git
 * [new branch]      ft/squashing -> ft/squashing
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES> git switch main
Switched to branch 'main'
Your branch is behind 'origin/main' by 5 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)
(base) PS C:\Users\Aime\TGxAUCA-BASIC-EXERCISES>
```

## Bundle5:

### Ex1:
