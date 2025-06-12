Vim macros (also called recordings) allow you to record a sequence of commands and keystrokes that you can play back later. When you see "recording @a" in the bottom left conrner of your Vim window, it means Vim is recording every keystroke you make into register 'a'.

### Starting and Stopping Recording
To start recording a macro:
1. Press `q` followed by a letter (a-z) to specify which register to use
2. For example, `qa` starts recording to register 'a'
3. you'll see "recording @a" appear in the status line.

To stop recording: 
1. Press `q` again while in normal mode 
2. The "recording" messaage will disappear

#### Playing back macros
Once you've recorded a macro, you can play it back usinng:
- `@a` to execute the macro stored in register 'a' 
- `@@` to repeat the last executed macro
- `5@a` to execute the macro in register 'a'  five times