---
id: remote-repos
aliases:
  - githubretard
tags:
  - rsrc
  - git
  - github
  - remote
---

1. Create a new repo on GitHub called like your local repo.
2. Don't add readme file and make sure its public.
3. Make sure u authenticated with your gh account in your terminal.
4. Add a remote to your repo.
```zsh
git remote add origin https://github.com/chickenwwwicken/repo.git
```
5. Run `git ls-remote` to make sure the remote was added correctly.
6. Push changes to the remote like this:
```zsh
git push origin main #or master, depending on how your main branch is set
```
7. I have a short alias for this
```zsh
gpo main/master
```
[g]it [p]ush [o]rigin

