Now that we have `pygame` installed, 
let's write just a bit of boilerplate code so that we have a runnable program to build on

## Assignment

1. Create a new file called `main.py`
2. On the first line, import `pygame`

``` python
import pygame
```

3. Write a main function that simply prints "Starting asteroids!" 
4. Add this exact statement to the end of the file: 

``` bash
if __name__ == "__main__":
	main()
```

This line ensures the `main()` function is only called when this file is run directly;
it won't run if it's imported as a module. 
It's considered the pythonic way to structure an executable program in Python. 
Technically the program will just wwork fine by just calling `main()` 
but you might get an angry letter if you don't:

5. Run the program with `python3 main.py`

![[asteroids2.png]]

---
[[2-Installation]]
[[4-Modules]]