Aggregate all the word and character data into a nice report that we can print 

Example:

```
--- Begin report of books/frankenstein.txt ---
77986 words found in the document

The 'e' character was found 46043 times
The 't' character was found 30365 times
The 'a' character was found 26743 times
The 'o' character was found 25225 times
The 'i' character was found 24613 times
The 'n' character was found 24367 times
The 's' character was found 21155 times
The 'r' character was found 20818 times
The 'h' character was found 19725 times
The 'd' character was found 16863 times
The 'l' character was found 12739 times
The 'm' character was found 10604 times
The 'u' character was found 10407 times
The 'c' character was found 9243 times
The 'f' character was found 8731 times
The 'y' character was found 7914 times
The 'w' character was found 7638 times
The 'p' character was found 6121 times
The 'g' character was found 5974 times
The 'b' character was found 5026 times
The 'v' character was found 3833 times
The 'k' character was found 1755 times
The 'x' character was found 677 times
The 'j' character was found 504 times
The 'q' character was found 324 times
The 'z' character was found 243 times
--- End report ---
```

### Converting dictionary into a list of dictionaries

#### Making list of dictionaries

Convert your dictionary of characters into a list of dictionaries and then use the `.sort()`

``` python
# making a list of dictionaries with this format {character : count}
def get_list_dicts(chars_dict):
    lista = []

    for item in chars_dict:
        single_dict = {}
        count = chars_dict[item]
        single_dict[item] = count
        lista.append(single_dict)    
    return lista
```

### Sort Function + List of Dictionaries

``` python
# getting a list of dictionaries but sorted from most appearances to least 
def get_sort_list(chars_dict):
    sorted_list = []
    # here is where you set the syntax for new dictionaries
    for char in chars_dict:
        sorted_list.append({'char': char, 'num': chars_dict[char]})
    # here is where you add your get_count function
    sorted_list.sort(reverse=True, key=get_count)
    return sorted_list

# getting the value (count) of each character and returning it so it can be used for sorting
def get_count(sorted_list):
    return sorted_list['num']
```

``` 
--- Output of get_sort_list(chars_dict) ---

[{'char': ' ', 'num': 74144}, {'char': 'e', 'num': 46043}, {'char': 't', 'num': 30365}, {'char': 'a', 'num': 26743}, {'char': 'o', 'num': 25225}, {'char': 'i', 'num': 24613}, {'char': 'n', 'num': 24367}, {'char': 's', 'num': 21155}, {'char': 'r', 'num': 20818}, {'char': 'h', 'num': 19725}, {'char': 'd', 'num': 16863}, {'char': 'l', 'num': 12739}, {'char': 'm', 'num': 10604}, {'char': 'u', 'num': 10407}, {'char': 'c', 'num': 9243}, {'char': 'f', 'num': 8731}, {'char': 'y', 'num': 7914}, {'char': '\n', 'num': 7652}, {'char': 'w', 'num': 7638}, {'char': 'p', 'num': 6121}, {'char': 'g', 'num': 5974}, {'char': ',', 'num': 5097}, {'char': 'b', 'num': 5026}, {'char': 'v', 'num': 3833}, {'char': '.', 'num': 3124}, {'char': 'k', 'num': 1755}, {'char': ';', 'num': 970}, {'char': '"', 'num': 796}, {'char': 'x', 'num': 677}, {'char': 'j', 'num': 504}, {'char': '-', 'num': 445}, {'char': 'q', 'num': 324}, {'char': 'z', 'num': 243}, {'char': '!', 'num': 239}, {'char': "'", 'num': 229}, {'char': '?', 'num': 220}, {'char': '1', 'num': 92}, {'char': ':', 'num': 68}, {'char': '(', 'num': 39}, {'char': ')', 'num': 39}, {'char': '*', 'num': 28}, {'char': '2', 'num': 24}, {'char': '/', 'num': 24}, {'char': '7', 'num': 23}, {'char': '0', 'num': 21}, {'char': '8', 'num': 20}, {'char': '3', 'num': 18}, {'char': '4', 'num': 17}, {'char': '5', 'num': 16}, {'char': '9', 'num': 13}, {'char': '6', 'num': 10}, {'char': '[', 'num': 4}, {'char': ']', 'num': 4}, {'char': '_', 'num': 2}, {'char': '@', 'num': 2}, {'char': '$', 'num': 2}, {'char': '#', 'num': 1}, {'char': '%', 'num': 1}]
```


## Printing Report

This was added to `main()`

``` python
# Printed book report
    print(f'--- Begin report of {book_path} ---')
    print('-------     by bookbot      -------')

    for item in sorted_list:
        
        # printint all letters
        if not item['char'].isalpha():
            continue
        print(f"'{item['char']}' character was found {item['num']} times")
    print("-----------------------------------")
    
    for item in sorted_list:

        # printing all extras
        if item['char'].isalpha():
            continue
        print(f"'{item['char']}' character was found {item['num']} times")
    print("-----------------------------------")

    print(f"Ammount of words in the book: {num_words}")
    
    print("-----------------------------------")
    
    print(f"--- End of book report {book_path} ---")
```

``` 
--- Output of main() --- 

--- Begin report of books/frankenstein.txt ---
-------     by bookbot      -------
'e' character was found 46043 times
't' character was found 30365 times
'a' character was found 26743 times
'o' character was found 25225 times
'i' character was found 24613 times
'n' character was found 24367 times
's' character was found 21155 times
'r' character was found 20818 times
'h' character was found 19725 times
'd' character was found 16863 times
'l' character was found 12739 times
'm' character was found 10604 times
'u' character was found 10407 times
'c' character was found 9243 times
'f' character was found 8731 times
'y' character was found 7914 times
'w' character was found 7638 times
'p' character was found 6121 times
'g' character was found 5974 times
'b' character was found 5026 times
'v' character was found 3833 times
'k' character was found 1755 times
'x' character was found 677 times
'j' character was found 504 times
'q' character was found 324 times
'z' character was found 243 times
-----------------------------------
' ' character was found 74144 times
'
' character was found 7652 times
',' character was found 5097 times
'.' character was found 3124 times
';' character was found 970 times
'"' character was found 796 times
'-' character was found 445 times
'!' character was found 239 times
''' character was found 229 times
'?' character was found 220 times
'1' character was found 92 times
':' character was found 68 times
'(' character was found 39 times
')' character was found 39 times
'*' character was found 28 times
'2' character was found 24 times
'/' character was found 24 times
'7' character was found 23 times
'0' character was found 21 times
'8' character was found 20 times
'3' character was found 18 times
'4' character was found 17 times
'5' character was found 16 times
'9' character was found 13 times
'6' character was found 10 times
'[' character was found 4 times
']' character was found 4 times
'_' character was found 2 times
'@' character was found 2 times
'$' character was found 2 times
'#' character was found 1 times
'%' character was found 1 times
-----------------------------------
Ammount of words in the book: 77986
-----------------------------------
--- End of book report books/frankenstein.txt ---

```

## Complete Function

``` python
def main():

    book_path = 'books/frankenstein.txt'
    
    # full text 
    text = get_book_text(book_path)
    
    # number of words in the text
    num_words = get_num_words(text)
    
    # dictionary of all the characters and their count in the text
    chars_dict = get_chars_dict(text)

    # list with all the {character:count}'s as dictionaries
    list_dicts = get_list_dicts(chars_dict)

    # sorted list of all character:count's ordered from most appearances to least
    sorted_list = get_sort_list(chars_dict)

    
    # here you can print tests
    # print(sorted_list)


    # Printed book report
    print(f'--- Begin report of {book_path} ---')
    print('-------     by bookbot      -------')

    for item in sorted_list:
        
        # printint all letters
        if not item['char'].isalpha():
            continue
        print(f"'{item['char']}' character was found {item['num']} times")
    print("-----------------------------------")
    
    for item in sorted_list:

        # printing all extras
        if item['char'].isalpha():
            continue
        print(f"'{item['char']}' character was found {item['num']} times")
    print("-----------------------------------")

    print(f"Ammount of words in the book: {num_words}")
    
    print("-----------------------------------")
    
    print(f"--- End of book report {book_path} ---")



# split all text to find the ammount of words
def get_num_words(text):
    words = text.split()
    return len(words)


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


# making a list of dictionaries with this format {character : count}
def get_list_dicts(chars_dict):
    lista = []

    for item in chars_dict:
        # setting a new dictionary for each character
        single_dict = {}
        # naming the values of dictionary as 'count' variable
        count = chars_dict[item]
        # adding new key/value pair to single_dict
        single_dict[item] = count
        # adding each single_dict to main list
        lista.append(single_dict)    
    return lista


# getting the value (count) of each character and returning it so it can be used for sorting
def get_count(sorted_list):
    return sorted_list['num']


# getting a list of dictionaries but sorted from most appearances to least 
def get_sort_list(chars_dict):
    sorted_list = []
    # here is where you set the syntax for your new dicitonaries
    for char in chars_dict:
        sorted_list.append({'char': char, 'num': chars_dict[char]})
    # here is where you connect with get_count function
    sorted_list.sort(reverse=True, key=get_count)
    return sorted_list



# gets the book from our path in pc, opens it, and reads it
def get_book_text(path):
    with open(path) as f:
        return f.read() 


main()
```

---
# End of BookBot

---
#### Next Course Object Oriented Programming
[[01projects/jpg/tech/bot.dev/2py/0_Resources/0.1_Contents|0.1_Contents]]
