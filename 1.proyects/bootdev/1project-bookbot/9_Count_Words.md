Add a new function that takes the text from the book as a string,
returns the number of words in the string.

Add a `print()` statement, then run your code to make sure it's good.
The Frankenstein book should contain `77986` words.

#### split the book
In python you can split a string on whitespace using the `.split()` method.

``` python
words = example_string.split()
```

### length of words in string

``` python
# split all text to find the ammount of words
def get_num_words(text):
    words = text.split()
    return len(words)
```


## All together

``` python
def main():    
	# set book path
    book_path = 'books/frankenstein.txt'
    # text is now the book using get_book_text
    text = get_book_text(book_path)
	# number of words in the text
    num_words = get_num_words(text)

	print(f'Dracula is {num_words} words long')


# split all text to find the ammount of words
def get_num_words(text):
    words = text.split()
    return len(words)


def get_book_text(path):
	# open file (books/frankenstein.txt) as f
    with open(path) as f:                    
	    # return contents of file with .read() method
        return f.read()        

# call main function
main()
```

---
[[8_Read_Files]]
[[10_Count_Chars]]