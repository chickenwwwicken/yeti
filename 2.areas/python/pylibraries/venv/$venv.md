Simply a self-contained location that enables you to maintain separate and isolated environments for your python projects

### Advantages
- manage dependencies
- manage versions
- manage packages
- * without conflicts across different projects

Allows each project to have its ownn set of installed packages without having to install them globally. 

Virtual Environments are just directories on our system
There are different environments you can use, for example: Poetry, python virtualenv, conda, pipenv

### Instructions
1. To create a venv
``` bash
python3 -m venv env # 'env' can be whatever u name it
```
2. To activate the venv
``` bash
source env/bin/activate
```
3. To deactivate the venv
``` bash
deactivate
```
4. Create a requirements.txt file
``` bash
pip freeze > requirements.txt
```
5. To install packages from a requirements.txt file
``` bash 
pip install -r requirements.txt
```

### common practice while downloading a python project from web

1. download repo
2. activate a new venv
3. pip install -r requirements.txt
4. 


---
- you can have multiple venvs on a single directory.
- 

