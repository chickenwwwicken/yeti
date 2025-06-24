Let's clone in our machine.

By creating a project on GitHub first and cloning it down,
The remote connection between ur local project and GitHub will be configured automatically.
If you start project on your local machine and push later, there's few more steps.

GitHub first = `git clone`
Machine first = `git init` `git remote add origin`

### Workspace Structure

1. Go to workspace root

``` bash
cd workspace
```

2. Create and cd into a dir called `github.com` 

``` bash
mkdir github.com
cd github.com
```

3. mkdir and cd into `chickenwwwicken` -> place to store all github repos 

``` bash
mkdir chickenwwwicken
cd chickenwwwicken
```

4. clone your `bookbot` repo by running this command inside `chickenwwwicken`

``` bash
git clone https://github.com/chickenwwwicken/bookbot
```

5. now new `bookbot` repo on your pc. cd into it

---
[[3_GitHub_Repo]]
[[5_First_Commit]]