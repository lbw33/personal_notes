title: Command Line Cheatsheet  
author: Luke Wickens  
output: html_document  

## Command Line Cheatsheet
  
<code>sudo</code>: allows root level permisson  
<code>alias</code> : allows for reassignment of a command *(e.g. alias open="xdg-open" will change the command "xdg-open" to "open")*  
<code>man [command]</code> : Displays manual for the specified [command].  
  
#### Current Location Commands  
<code>pwd</code> : Shows the current user directory listed. Given from the absolute path (root).  
<code>ls</code>: Shows what files are in the current directory.  
<code>ls -a</code>: Shows all files in the current directory (including hidden files).  

#### Movement Commands
<code>cd [name]</code> : Go to specified directory.  
<code>cd ..</code> : Go one directory up (back to previous directory).  
<code>cd /</code> : Go to root directory.  
<code>cd ~</code> : Go to user directory.  

#### Creation/Deletion Commands

<code>mkdir [name]</code> : Creates a new folder in the current directory.  
<code>rmdir [name]</code> : Removes the file specified **(This only works on empty folders. For folders containing files see rm) -r.**  
<code>rm -r [name]</code> : Removes a folder that is either empty or contains files.  
<code>rm [name]</code> : Removes the file specified.  
<code>rm -i</code> : *Interactive* Requires user confirmation before deletion.  
<code>rm -f</code> : Force removes a file *(Works on write-protected files)*.  
<code>touch [name]</code> : Creates a file (specified file type i.e. .txt, .html, .js etc).  
<code>cat > [name]</code> : Creates a text file and allows user to type contents into Terminal. 


#### Open Commands

<code>open [name]</code> : Opens a file in the current diretory *("xdg-open" in Ubuntu)*.  
<code>gedit [name]</code> : Opens a file using GNOME text editor *(Ubuntu)*.  
<code>open -a [name]</code> : Opens the specified application.  
> <code>code .</code> : Opens Visual Studio Code.  

<code>open -a "Visual Studio Code" [name]</code> : Opens the specified file [name] with the specified application.  

#### File Manipulation

<code>cp [name] [new_name]</code> : Copies the [name] file to [new_name].  
<code>mv [name] [new_name]</code> : Renames [name] to [new_name].  
<code>mv [name] [location]</code> : Moves specified file to the location specified.  
<code>cat [name]</code> : Displays a concatenated version of the files contents.  
<code>cat >> [name]</code> : Appends user input to specified text file.  
<code>cat [name] [other_name]</code> : Combines [name] and [other_name] text files.  
<code>head -[number]</code> : Displays the first [number] of lines in a text file.  
<code>tail -[number]</code> : Displays the last [number] of lines in a text file.  
<code>less [name]</code> : Displays large text files. Allows the user to scroll through the file *("q" quits the file).*  
<code>[command1] | [command2]</code> : Pipe the output from [command1] into [command2] *(e.g. whois google.com | head = returns the whois of google.com passed through the head command to only return the first 10 lines)*  

#### Searching

<code>find [folder] -name [name]</code> : Finds the file [name] in the specified [folder].  
<code>grep [word] [name]</code> : Search for a specified [word] in the specified text file [name].  
><code>grep [word] [name] -v</code> : Displays all lines that **do not** match the specified [word].  
<code>grep [word] [name] -n</code> : Displays the line number where the specified [word] can be located in the text file preceeding the text.  
<code>grep [word] [name] -c</code> : Displays the line number where the specified [word] can be located in the text *Standalone*  
<code>grep [word] [name] -i</code> : Ignores the case of the specified [word].  

<code>wc [name]</code> : Displays the line count, the word count and the character count of the specified text file.  
<code>wc [name] -l</code> : Displats the line count of the text file.  
<code>wc [name] -w</code> : Displats the word count of the text file.  
<code>wc [name] -c</code> : Displats the character count of the text file.  
<code>history</code> : Displays the history of commands passed into Terminal.

### Permissions

<code>whoami</code> : Displays the current user.  
<code>ls -l</code> : Displays file permissions.  
>If the first character in the file permissions is "**-**" this denotes that it is a file.  
    If the first character in the file permissions is "**d**" this denotes that it is a directory.  
    "**r**" : Read permission access.  
    "**w**" : Write permission access.  
    "**x**" : Execute permission access.  
    "**-**" : *Excluding first character* Access to that element is unavailable for that user.  
    
<code>chmod [permission] [name]</code> : Changes the permissions of the specified file.  
>*7* is rwx *(e.g. 777 = user, group and global can all rwx)*  
    *6* is rw *(e.g. 766 = user can rwx but group and global can only rw)*  
    *5* is rx *(e.g. 755 = user can rwx but group and global can only rx)*  
    *4* is r *(e.g. 744 = user can rwx but group and global can only r)*  

#### Example

>*-rw-rw-r-- 1 luke luke      0 Oct 23 19:18  goodbye.txt*  
*drwxrwxr-x 2 luke luke   4096 Oct 23 18:11  Makers*

The first character denotes file/directory(folder).  
2, 3, 4 characters denote permissions for the current user.  
5, 6, 7 characters denote permissions for the group.  
8, 9, 10 characters denote permissions for the global. 

### Environment

<code>env</code> : Displays environment variables.  
<code>echo $[variable]</code> : Displays specified environment [variable].   
<code>rvm use [version]</code> : Switches version of Ruby currently being used to [version].  

### Processes

<code>ps</code> : Displays current processes.  
<code>ps x</code> : Displays all processes currently running on the computer.


