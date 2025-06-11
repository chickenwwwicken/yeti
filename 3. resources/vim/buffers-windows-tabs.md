``` 
:help :wincmd
```
Summary:
	A buffer is the in-memory text of a file.
	A window is a viewport on a buffer. 
	A tab page is a collection of windows.

- you can have two windows showing the same buffer

`CTRL+W c` - close window

##### [[Buffers]]
A buffer can be in one of three states:
***active***: The buffer is displayed in a window. If there is a file for this buffer, it has been read into the buffer. the buffer may have been modified since then and thus be different from the file. 
***hidden***: The buffer is not displayed. If there is a file for this buffer, it has been read into the buffer. Otherwise it's the same as an active buffer, you just can't see it.
***inactive***: The buffer is not displayed and does not contain anything. Options for the buffer are remembered if the file was once loaded. It can contain marks from the shada file. But the buffer doesn't contain text. 

in a table:
**state**        **displayed**      **loaded**        **":buffers"**
             **in window**                    **shows** 
active         yes           yes           'a'
hidden         no            yes           'h'
inactive       no            no            ' ' 







