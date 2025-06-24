### Download Frankenstein

Frankenstein book by Mary Shelley is public domain.

Download here [Frankenstein](https://raw.githubusercontent.com/asweigart/codebreaker/master/frankenstein.txt) 

Create a dir in `bookbot` called `books` 
Right-click the text on the webpage and `Select All` 
copy pasta into a frankenstein.txt in the `books` dir.

### Use a .gitignore file

We don't save entire book in our Git repo. 
Git is for code not for data.

Create a `.gitignore` file in the root of project and add this text:

``` 
books/
```

Now whenever u run `git add` from the root,
all the files in the `books` dir will be automatically ignored.

### Read the book

Change `main.py` so that instead of printing 'hello world' it reads 'frankenstein.txt' 
and prints it all to the console. 

``` python
def main():    
	# set book path
    book_path = 'books/frankenstein.txt'
    # text is now the book using get_book_text
    text = get_book_text(book_path)
    # print it to the console
    print(text)
    
    
def get_book_text(path):
	# open file (books/frankenstein.txt) as f
    with open(path) as f:                    
	    # return contents of file with .read() method
        return f.read()        

# call main function
main()
```

---
[[7_Running_Python]]
[[9_Count_Words]]

