Add a new function that takes the text from the book as a string
and returns number of times each character appears in the string.
Convert any character to lowercase, no duplicates.

#### Hints

Recommended to use a dictionary of `String` : `Integer` 
Something like this:

```
{'p': 6121, 'r': 20818, 'o': 25225, ...
```

### Converting to lowercase

To convert a string to lowercase use the `.lower()` method

``` python
my_string = "FOR FRODO"
lowered_string = my_string.lower()
print(lowered_string)
# for frodo
```

## counting letters + lowercase

``` python
# counting how many times each letter appears in text
def get_chars_dict(text):
    low_caps = text.lower()
    char_counts = {}
    for char in low_caps:
        if char not in char_counts:
            char_counts[char] = 1
        else:
            char_counts[char] += 1
    return char_counts
```

```
{'p': 6121, 'r': 20818, 'o': 25225, 'j': 504, 'e': 46043, 'c': 9243, 't': 30365, ' ': 74144, 'g': 5974, 'u': 10407, 'n': 24367, 'b': 5026, "'": 229, 's': 21155, 'f': 8731, 'a': 26743, 'k': 1755, 'i': 24613, ',': 5097, 'y': 7914, 'm': 10604, 'w': 7638, 'l': 12739, '(': 39, 'd': 16863, ')': 39, 'h': 19725, '\n': 7652, 'v': 3833, '.': 3124, '-': 445, ':': 68, '1': 92, '7': 23, '2': 24, '0': 21, '8': 20, '[': 4, '#': 1, '4': 17, ']': 4, '*': 28, 'z': 243, '?': 220, ';': 970, 'x': 677, 'q': 324, '!': 239, '"': 796, '3': 18, '5': 16, '9': 13, '6': 10, '_': 2, '/': 24, '%': 1, '@': 2, '$': 2}
```

## Complete main.py

``` python
def main():    
	# set book path
    book_path = 'books/frankenstein.txt'
    # text is now the book using get_book_text
    text = get_book_text(book_path)
    # number of words in the text
    num_words = get_num_words(text)
    # dictionary of all the characters and their count in the text
    chars_dict = get_chars_dict(text)
	print(chars_dict)


# counting how many times each letter appears in text
def get_chars_dict(text):
    low_caps = text.lower()
    char_counts = {}
    for char in low_caps:
        if char not in char_counts:
            char_counts[char] = 1
        else:
            char_counts[char] += 1
    return char_counts


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
[[9_Count_Words]]
[[11_Print_Report]]