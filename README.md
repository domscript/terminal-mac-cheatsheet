# Terminal Cheatsheet for Mac (Basics)

---

**[SHORTCUTS](#shortcuts)**

**[CORE COMMANDS](#core-commands)**

**[CHAINING COMMANDS](#chaining-commands)**

**[PIPING COMMANDS](#piping-commands)**

**[COMMAND HISTORY](#command-history)**

**[FILE MANAGEMENT](#file-management)**

**[DIRECTORY MANAGEMENT](#directory-management)**

**[FILE SIZE AND DISK SPACE](#file-size-and-disk-space)**

**[SEARCH](#search)**

**[HOMEBREW](#homebrew)**

**[HELP](#help)**

**[LIST DIRECTORY CONTENTS](#list-directory-contents)**

**[PERMISSIONS](#permissions)**

**[PROCESSES](#processes)**

**[NETWORK](#network)**

**[ENVIRONMENT VARIABLE OR PATH](#environment-variable-or-path)**

**[OUTPUT](#output)**

---

## SHORTCUTS

| Key/Command     | Description                                                                                                                                       |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| Ctrl + a        | Go to the beginning of the line you are currently typing on. This also works for most text input fields system wide. Netbeans being one exception |
| Ctrl + e        | Go to the end of the line you are currently typing on. This also works for most text input fields system wide. Netbeans being one exception       |
| Ctrl + l        | Clears the Screen                                                                                                                                 |
| Cmd + k         | Clears the Screen                                                                                                                                 |
| Ctrl + u        | Cut everything backwards to beginning of line                                                                                                     |
| Ctrl + k        | Cut everything forward to end of line                                                                                                             |
| Ctrl + w        | Cut one word backwards using white space as delimiter                                                                                             |
| Ctrl + y        | Paste whatever was cut by the last cut command                                                                                                    |
| Ctrl + h        | Same as backspace                                                                                                                                 |
| Ctrl + c        | Kill whatever you are running. Also clears everything on current line                                                                             |
| Ctrl + d        | Exit the current shell when no process is running, or send EOF to a the running process                                                           |
| Ctrl + z        | Puts whatever you are running into a suspended background process. fg restores it                                                                 |
| Ctrl + \_       | Undo the last command. (Underscore. So it's actually Ctrl + Shift + minus)                                                                        |
| Ctrl + t        | Swap the last two characters before the cursor                                                                                                    |
| Ctrl + f        | Move cursor one character forward                                                                                                                 |
| Ctrl + b        | Move cursor one character backward                                                                                                                |
| Option + ???      | Move cursor one word forward                                                                                                                      |
| Option + ???      | Move cursor one word backward                                                                                                                     |
| Esc + t         | Swap the last two words before the cursor                                                                                                         |
| Esc + Backspace | Cut one word backwards using none alphabetic characters as delimiters                                                                             |
| Tab             | Auto-complete files and folder names                                                                                                              |

## CORE COMMANDS

| Key/Command    | Description                                                               |
| -------------- | ------------------------------------------------------------------------- |
| cd [folder]    | Change directory e.g. `cd Documents`                                      |
| cd             | Home directory                                                            |
| cd ~           | Home directory                                                            |
| cd /           | Root of drive                                                             |
| cd -           | Previous directory                                                        |
| cd ..          | Move up to the parent directory                                           |
| cd../..        | Move up two levels                                                        |
| ls             | Short listing                                                             |
| ls -l          | Long listing                                                              |
| ls -a          | Listing incl. hidden files                                                |
| ls -lh         | Long listing with Human readable file sizes                               |
| ls -R          | Entire content of folder recursively                                      |
| sudo [command] | Run command with the security privileges of the superuser (Super User DO) |
| open [file]    | Opens a file ( as if you double clicked it )                              |
| top            | Displays active processes. Press q to quit                                |
| nano [file]    | Opens the file using the nano editor                                      |
| vim [file]     | Opens the file using the vim editor                                       |
| clear          | Clears the screen                                                         |
| reset          | Resets the terminal display                                               |

## CHAINING COMMANDS

| Key/Command                  | Description                                          |
| ---------------------------- | ---------------------------------------------------- |
| [command-a]; [command-b]     | Run command A and then B, regardless of success of A |
| [command-a] && [command-b]   | Run command B if A succeeded                         |
| [command-a] \|\| [command-b] | Run command B if A failed                            |
| [command-a] &                | Run command A in background                          |

## PIPING COMMANDS

| Key/Command                | Description                                                                      |
| -------------------------- | -------------------------------------------------------------------------------- |
| [command-a] \| [command-b] | Run command A and then pass the result to command B e.g ps auxwww \| grep google |

## COMMAND HISTORY

| Key/Command | Description                                                          |
| ----------- | -------------------------------------------------------------------- |
| history n   | Shows the stuff typed ??? add a number to limit the last n items       |
| Ctrl + r    | Interactively search through previously typed commands               |
| ![value]    | Execute the last command typed that starts with ???value???              |
| ![value]:p  | Print to the console the last command typed that starts with ???value??? |
| !!          | Execute the last command typed                                       |
| !!:p        | Print to the console the last command typed                          |

## FILE MANAGEMENT

| Key/Command                                | Description                                                                                                  |
| ------------------------------------------ | ------------------------------------------------------------------------------------------------------------ |
| touch [file]                               | Create a new file                                                                                            |
| pwd                                        | Full path to working directory                                                                               |
| .                                          | Current folder, e.g. `ls .`                                                                                  |
| ..                                         | Parent/enclosing directory, e.g. `ls ..`                                                                     |
| ls -l ..                                   | Long listing of parent directory                                                                             |
| cd ../../                                  | Move 2 levels up                                                                                             |
| cat                                        | Concatenate to screen                                                                                        |
| rm [file]                                  | Remove a file, e.g. `rm data.tmp` (This deletes the file permanently; use with caution.)                     |
|                                            |
| rm -i [file]                               | Remove a file only when you give confirmation                                                                |
| rm -r [dir]                                | Remove a directory and contents                                                                              |
| rm -f [file]                               | Force removal without confirmation                                                                           |
| rm [file1] [file2] [file3]                 | Delete multiple files without any confirmation                                                               |
|                                            |
| cp [file] [newfile]                        | Copy file and give it custom name in the current directory                                                   |
| cp [file] [dir]                            | Copy file to directory                                                                                       |
| cp [file]~/[dir]/[newfile]                 | Copy a file to the directory and rename the copied file                                                      |
| cp -R [dir] ["newdir"]                     | Copy a directory to a new directory with spaces in the filename                                              |
| cp -i [file] [dir]                         | Prompts you before copying a file with a warning overwrite message                                           |
| cp [file1] [file2] [file3] \/[dir1]/[dir2] | Copy multiple files to a directory                                                                           |
| ditto -V [dirpath]/[newdir]                | Copy the contents of a directory to new directory. In here "-V" print a line of status for every file copied |
| mv [file] [newfilename]                    | Move/Rename, e.g. `mv file1.ad /tmp`                                                                         |
| mv [file] [dir]                            | Move a file to the directory, possibly by overwriting an existing file                                       |
| mv -i [file] [dir]                         | Optional -i flag to warn you before overwriting the file                                                     |
| mv \*.png ~/[dir]                          | Move all PNG files from current directory to a different directory                                           |
| pbcopy < [file]                            | Copies file contents to clipboard                                                                            |
| pbpaste                                    | Paste clipboard contents                                                                                     |
| pbpaste > [file]                           | Paste clipboard contents into file, `pbpaste > paste-test.txt`                                               |

## DIRECTORY MANAGEMENT

| Key/Command             | Description                                               |
| ----------------------- | --------------------------------------------------------- |
| mkdir [dir]             | Create new directory                                      |
| mkdir -p [dir]/[dir]    | Create nested directories                                 |
| mkdir [dir] [dir] [dir] | Create several directories at once                        |
| mkdir ["dir"]           | Create a directory with a space in the filename           |
| rmdir [dir]             | Remove directory ( only operates on empty directories )   |
| rm -R [dir]             | Remove directory and contents                             |
| less [file]             | Output file content delivered in screensize chunks        |
| [command] > [file]      | Push output to file, keep in mind it will get overwritten |
| [command] >> [file]     | Append output to existing file                            |
| [command] < [file]      | Tell command to read content from a file                  |

## FILE SIZE AND DISK SPACE

| Command              | Action                                                                                                             |
| -------------------- | ------------------------------------------------------------------------------------------------------------------ |
| du                   | List usage for each subdirectory and its contents                                                                  |
| du -sh [folder]      | Human readable output of all files in a directory                                                                  |
| du -s                | Display an entry for each specified file                                                                           |
| df -h                | Calculate your system's free disk space                                                                            |
| df -H                | Calculate free disk space in powers of 1,000                                                                       |
| du -sk\* \| sort -nr | List files and folders, totaling the size including the subfolders. Replace sk* with sm* to list directories in MB |

## SEARCH

| Key/Command                          | Description                                                                                               |
| ------------------------------------ | --------------------------------------------------------------------------------------------------------- |
| find [dir] -name [search_pattern]    | Search for files, e.g. `find /Users -name "file.txt"` Use wildcards (\*) to search for parts of filenames |
| grep [search_pattern] [file]         | Search for all lines that contain the pattern, e.g. `grep "Tom" file.txt`                                 |
| grep -r [search_pattern] [dir]       | Recursively search in all files in specified directory for all lines that contain the pattern             |
| grep -v [search_pattern] [file]      | Search for all lines that do NOT contain the pattern                                                      |
| grep -i [search_pattern] [file]      | Search for all lines that contain the case-insensitive pattern                                            |
| grep -rl ["text"] [dir]              | Search for all files containing [text] inside [dir]                                                       |
| mdfind [search_pattern]              | Spotlight search for files (names, content, other metadata), e.g. `mdfind skateboard`                     |
| mdfind -onlyin [dir] -name [pattern] | Spotlight search for files named like pattern in the given directory                                      |

## HOMEBREW

| Command                          | Action                                                                   |
| -------------------------------- | ------------------------------------------------------------------------ |
| brew doctor                      | Check brew for potential problems                                        |
| brew help                        | List of useful homebrew formula and cask commands                        |
| brew list --formula              | List only installed formulas                                             |
| brew list --cask                 | List only installed cask                                                 |
| brew outdated --formula          | Search for outdated formula                                              |
| brew outdated --cask             | Search for outdated cask                                                 |
| brew outdated [formula]\|[cask]  | Search for outdated formula or cask                                      |
| brew pin [installed_formula]     | Pin a formula from getting upgraded                                      |
| brew unpin [installed_formula]   | Unpin to upgrade a package                                               |
| brew install [formula]\|[cask]   | Install a formula or cask                                                |
| brew uninstall [formula]\|[cask] | Uninstall a formula or cask                                              |
| brew deps [formula]\|[cask]      | List all the dependencies of a formula or cask                           |
| brew search text \|/regex/       | Search formula or cask through regex                                     |
| brew upgrade [formula]\|[cask]   | Upgrade the formula or cask                                              |
| brew cleanup                     | Remove stale lock files and outdated packages for all formula and casks. |

## HELP

| Key/Command              | Description                                       |
| ------------------------ | ------------------------------------------------- |
| [command] -h             | Offers help                                       |
| [command] --help         | Offers help                                       |
| info [command]           | Offers help                                       |
| man [command]            | Show the help manual for [command]                |
| whatis [command]         | Gives a one-line description of [command]         |
| apropos [search-pattern] | Searches for command with keywords in description |

## LIST DIRECTORY CONTENTS

| Command | Action                                                                                                                            |
| ------- | --------------------------------------------------------------------------------------------------------------------------------- |
| ls      | Display the name of files and subdirectories in the directory                                                                     |
| ls -C   | Force multi-column output of the listing                                                                                          |
| ls -a   | List all entries including those with . and ..                                                                                    |
| ls -1   | Output the list of files in one entry per line format                                                                             |
| ls -F   | Display a / immediately after each path that is a directory, \* after executable programs or scripts, and @ after a symbolic link |
| ls -S   | Sort files or entries by size                                                                                                     |
| ls -l   | List in a long format. Includes file mode, owner and group name, date and time file was modified, pathname, and more              |
| ls -l / | List of the file system from root with symbolic links                                                                             |
| ls -lt  | List the files sorted by time modified (most recent first)                                                                        |
| ls -lh  | Long listing with human readable file sizes in KB, MB, or GB                                                                      |
| ls -lo  | List the file names with size, owner, and flags                                                                                   |
| ls -la  | List detailed directory contents, including hidden files                                                                          |

## PERMISSIONS

| Command                     | Action                                                                              |
| --------------------------- | ----------------------------------------------------------------------------------- |
| ls -ld                      | Display the default permission for a home directory                                 |
| ls -ld \/[dir]              | Display the read, write, and access permission of a particular folder               |
| chmod 755 [file]            | Change the permission of a file to 755                                              |
| chmod -R 600 [dir]          | Change the permission of a folder (and its contents) to 600                         |
| chown [user]:[group] [file] | Change the ownership of a file to user and group. Add -R to include folder contents |

## PROCESSES

| Command                  | Action                                                                                                                                    |
| ------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------- |
| ps -ax                   | Output currently running processes. Here, a shows processes from all users and x shows processes that are not connected with the Terminal |
| ps -aux                  | Shows all the processes with %cpu, %mem, page in, PID, and command                                                                        |
| top                      | Display live information about currently running processes                                                                                |
| top -ocpu -s 5           | Display processes sorted by CPU usage, updating every 5 seconds                                                                           |
| top -o rsize             | Sort top by memory usage                                                                                                                  |
| kill PID                 | Quit process with ID [PID]. You'll see PID as a column in the Activity Monitor                                                            |
| ps -ax \| grep [appname] | Find a process by name or PID                                                                                                             |

|

## NETWORK

| Command                               | Action                                                                                                       |
| ------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| ping [host]                           | Ping host and display status                                                                                 |
| whois [domain]                        | Output whois info for a domain                                                                               |
| curl -O [url/to/file]                 | Download file via HTTP, HTTPS, or FTP                                                                        |
| ssh [username]@[host]                 | Establish SSH connection to [host] with user [username]                                                      |
| scp [file] [user]@[host]:/remote/path | Copy [file] to a remote [host]                                                                               |
| arp -a                                | View a list of all devices on your local network. It will show you the IP and MAC address of all the devices |
| ifconfig en0                          | View your device IP and MAC address                                                                          |
| traceroute [hostname]                 | Identify the path and the hops traversed by the packets from your device to the destination address          |

## ENVIRONMENT VARIABLE OR PATH

| Command                                     | Action                                                                                         |
| ------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| printenv                                    | Display a list of currently set environment variables. Also tells you which shell you're using |
| $echo                                       | Tells the terminal to print something and show it to you                                       |
| echo $PATH                                  | Check the value of the PATH variable which storea a list of directories with executable files  |
| echo $PATH >path.txt                        | Export the path directory to a text file                                                       |
| export PATH=$PATH:absolute/path to/program/ | Execute a program via terminal only in your current session                                    |

## OUTPUT

| Command          | Action                                                                                 |
| ---------------- | -------------------------------------------------------------------------------------- |
| cat [file]       | Output the content of [file]                                                           |
| less [file]      | Output the contents of [file] using the less command that supports pagination and more |
| head [file]      | Output the first 10 lines of [file]                                                    |
| [cmd] > > [file] | Appends the output of [cmd] to [file]                                                  |
| [cmd] > [file]   | Direct the output of [cmd] into [file]                                                 |
| [cmd1] \| [cmd2] | Direct the output of [cmd1] to [cmd2]                                                  |
