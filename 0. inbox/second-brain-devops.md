Building a System for a Second Brain

1. A second brain
2. Concepts
3. taking notes
4. a process

Book References
1. Building a Second Brain
2. 7 Habits of Highly Efficient People
3. Meditations Marcus Aurelius

"The happiness of your life depends upon the quality of your thoughts."
- Marcus Aurelius

"Your professional success and quality of life depend directly on your
ability to mannage information effectively."
- Tiago Forte

"Writing distills, crystallizes, and clarifies thought and helps break 
the whole into parts."
- The 7 habits of highly effective people

## Why take notes
We good at processing info
around 300-400MiB of data every day
we not good at storing info

"you can research your own brain"

our biological mind is hardware made 10,000 years ago
taking notes is a way of offloading this information
and keeping it in a long term storage
systems for storing this information helps us utilize it in the future. 

## The Problem
Hard to edit, backup, sync,
store, fetch, code, manipulate.
Some programs work good for some but not for every case.
We want something that's perfect. 

## Obsidian
- own your notes
- markdown
- visuals
- plugins
- links

## Neovim
- motions
- editing text
- finder 
- plugins
- all the gud stuff

# Time to Build
1. build the structure
2. Obsidian and plugins for maximum efficiency
3. neovim with obsidian
4. techniques for neovim writers
5. syncing and backups

# 1. Building a Second Brain
C - Capture "Keep what resonates"
O - Organize "Save for Actionability"
D - Distill "Find the Essence"
  - progressive summarization
  - when you take note summarize
  - taking a large piece of content (article)
  - go to most important paragraph
  - underline most important sentence
  - keep in bold most important keyword
E - Express "Show your work"
  - write it in a sentence or two or three in your own words
  - forcing your brain to create new connections 
    
# 2. CODE -> PARA
P - Project
  - Short term efforts in your work or life that you're working on now
  - Has a time of start and a time of end.
A - Area
  - Long term responsibilities you want to mannage over time
  -     health
  -     recipes
  -     finances
  -     relationships
  -     philosophy
  -     coding and machines
  -     second brain
  -     home & personal dox
R - Resources
  - Topics or interests that may be useful in the future
  - atomic pieces of information that can be useful
  - works for git commands or python basics
A - Archive
  - Inactive items from the other three categories
  - Areas or Projects that or Resources are not part of your life anymore

# 3. Obsidian
### keybinds
- ctrl + e - toggle edit mode
- ctrl + , - open settings
- ctrl + p - command palette
- ctrl + n - create note

### structure
- 0. inbox
- 1. proyects
- 2. areas
- 3. resources
- 4. archive
- templates

### configuration
##### editor
- enable vim key bindings
- show line numbers

##### core plugins -> templates
- select your TEMPLATES directory

##### community plugins
- Dataview -> install -> enable
- git -> install -> enable
- vimrc support -> install -> enable
    -> configuration -> display mode display

##### appearance
- dark mode
- source code pro font on all

##### .obsidian.vimrc file
this file goes right at the root of vault/dir
added this and also gonna add it for neovim
```.obsidian.vimrc
imap jj <Esc>
```
changes Esc key to just 'jj' epic honestly game changer.

### markdown
##### yaml properties
add "---" @ first line
- aliases - anything you wanna call your file also
- tags - helpful to separate between music books art coding
- checkbox - add lil true false for done or not

##### dataview
add "```" and dataview as the type
now you can query with your tags
these queries automatically update, for example:
- when you set a query for all files with resource tag
- when you add a new file with resource tag
- and go back to the original query, kuchau, updated

### templates
we've explained how to use the dataview query for updated lists of files
we can use templates to automatically be added to whatever list its tagged.

#### dataview
example for a dataview query
```dataview
list
from #<any-tag-u-want> and !"templates"
sort file.name
```

#### list of templates to do:
- boot dev note with questions
- boot dev exercise
- boot dev index of chapter
- boot dev index of chapters
- run zsh file
- scroll?
- youtube video guide

# 4 neovim
Quick recap
- motions
- frictionless

all you need is Telescope.nvim
but it helps to have Obsidian.nvim 
























