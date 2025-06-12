To remove all of a programs specific files and dependencies all across your Linux filesystem use these two commands

`sudo apt purge <program>`
`sudo apt autoremove <program>`

these commands don't have authorization to touch your home FS so delete the files of the program in the .config folder manually