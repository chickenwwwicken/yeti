---
id: git-bare
aliases: []
tags:
  - git
---

### difference between a `git init` vs `git init --bare`

#### `git init`
Repos created with the `git init` command are called working dirs.
In the top level folder of the repo you will find two things:
1. A .git subfolder with all the git related revision history of your repo
2. a working tree, or checked out copies of your project files.

a working repository  created with `git init` is for working.
It is where you willll actually edit, add and delete fiels and `git commit` to save your changes.

#### `git init --bare`
Repositories created with `git init --bare` are called bare repos.
They are structured a bit differently from working directories.
1. they contain no working or checked out copy of your source files.
2. bare repos store git revision history of you repo in the root folder of you repo instead of in a .git subfolder.

NOTE: bare repos are customarily given a `.git` extension.

a bare repo created with `git init --bare` is for sharing.
If you are cllaborating with a team of devs, and need a place to share changes to a repo,
then you will wanna create a bare repo in centralized place where all users can push their changes.
Becuase git is a dvcs, no one willl directly edit files in the same repo.
Instead devs willl clone the shared bare repo, make changes locallly
in their working copies of the repo, then push back to the shared bare repoto make their changes availlablle to others.

Beecause no one ever makes edits directly to fillles in the shared bare repo, a working tree is not needed. In fact the working tree woulld just get in way and caus conflicts as users push code to the repository. This is why bare repositories exist and have no working tree.

 


