# Bash course notes

**All bash scripts have three core components**
- The shebang line (#!/bin/bash)
- Commands
- Exit statement (0 = succsessful; 1-255 = unsuccsessful)

Scripts can be given execute persmissions with the chmod command.
```bash
chmod +x hello_world.bash
```

# File permissions
Which users can perform certain actions on a given file?
```bash
# view file permissions 
ls -l

# r = read
# w = write
# x = execute
# - = cannot r, w, x
drwxr-xr-x   3 Dylan.Morison.Software  staff   96 May 15 12:33 Sid Meier's Civilization VI
drwxr-xr-x   3 Dylan.Morison.Software  staff   96 Apr  2 16:04 coding_playground
drwxr-xr-x  10 Dylan.Morison.Software  staff  320 Jul 12 11:33 courses
drwxr-xr-x   5 Dylan.Morison.Software  staff  160 Mar 28 12:02 password manager
drwxr-xr-x   6 Dylan.Morison.Software  staff  192 May 14 17:24 projects
```
Here are what the following characters represent: 
1. If directory, d. Else, file.
2. File owner's permissions, file owner is showed in column 3 above (Dylan.Morison.Software)
3. File owner's permissions, file owner is showed in column 3 above (Dylan.Morison.Software)
4. File owner's permissions, file owner is showed in column 3 above (Dylan.Morison.Software)
5. File group permissions, 4th column above (staff)
6. File group permissions, 4th column above (staff)
7. File group permissions, 4th column above (staff)
8. Anyone who is not file owner and not part of file group
9. Anyone who is not file owner and not part of file group
10. Anyone who is not file owner and not part of file group

Generally speaking, only the file owner should be able to run or write the script.
```bash
# give file owner r, w, x, everyone else only r 
chmod 744 hello_world.bash
```
[permissions calculator](http://permissions-calculator.org/)

# Adding Scripts to the PATH

The systems path is a variable that tells the shell which directories to search for executable files in. To look at the systems path, run the command
```bash
echo "$PATH"

#output
/Users/Dylan.Morison.Software/.nvm/versions/node/v16.4.2/bin:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin
```
All we're seeing is a set of paths to folders, each seperated by a colon.

# Shell Expansions
Shell expansions are very powerful features that allow us to retrieve data, process command output, and perform calculations. 

There are three different types of shell paramters:
- Variables
  - User defined variables, `name=value`
  - Shell variables
    - Bourne Shell Variables
    - Bash Shell Variables 
- Positional paramters
- Special paramteres


It turns out that the **PATH** variable is actually a Bourne Shell variable, as is the **HOME** variable and **USER** variable.
- HOME
- USER
- HOSTNAME
- HOSTTYPE
- PS1 
