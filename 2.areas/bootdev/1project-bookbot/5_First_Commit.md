Git commits are used to save snapshots of your code at a specific point in time.
Each commit should represent a single logical change to your codebase.
examples: 
- add a new feature
- fix a new bug
- rework a bit of your code to be more readable.

### Make a Code Change

Open your `README.md` file and add this to it.

```
BookBot is my first project!
```

### View your diff

A 'diff' is a visual aid that shows you the differences between two files. 
This only works in VS Code kekw.

### Stage the Change

``` bash
# Stage the change
git add . 

# Commit the change w message
git commit -m 'update readme with a description'

# Push to Github
git push origin main
# origin refers to the remote repo on GitHub
# main refers to the branch you are pushing ur changes into
```

There is a `main` in the github `remote` repo (`bookbot`) 
Another `main` in your local, looks like each has its own hash

![[ssbookbot5.1.png]]

---
[[4_Git_Clone]]
[[6_Installing_Python]]