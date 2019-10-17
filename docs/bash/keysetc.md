# Introduction to the Linux/Mac OS command line

ECRL tools are developed and run locally on Linux servers and Mac OS computers. All of these computers are based on a version of Linux that uses the Bourne Again Shell (BASH) for developing project code and controlling software execution. So a basic knowledge of Bash commands and scripting tools is essential. 

### By default, the terminal command line prompt on machines managed by Cornell IT shows the machine name followed by the user's NetID and 2 right arrows :

>  **AG-EAS-12345678: mynetid >>**

# Bash Command Line Fundamentals
### Learning these handy command line shortcuts before you start typing complex commands will make your life a whole lot easier. 

## **_Moving the cursor and editting text_**
#### **NOTE : _```deleted```_** characters **_are not_** recoverable,

Keys | Action
------- | ------
**```Ctrl A```** | Move cursor to beginning of current line.
**```Ctrl B```** | Move cursor ```B```ack (left) one character.
**```Ctrl D```** | ```D```elete character under cursor.
**```Ctrl E```** | Move cursor to ```E```nd of current line.
**```Ctrl F```** | Move cursor ```F```orward (right) one character.
**```Ctrl T```** | Swap the last 2 charcters before the cursor.
**```Esc T```** | Swap the last 2 words before the cursor.

#### **_Cut and paste_**. Unlike deleted characters, &nbsp;```cut``` characters can be put back.

Keys | Action
------- | ------
**```Ctrl K```** | Cut from from cursor to end of current line.
**```Ctrl U```** | Cut from beginning of current line to the cursor.
**```Ctrl W```** | Cut the word before the cursor.
**```Ctrl Y```** | Paste previous cut string at cursor position.

#### **_Be carefuli when using ```Ctrl U``` at the end of a line because it iwll cut the entire line._**

#### **_Linux and Mac OS use different key combinations for some shortcuts. On a Mac, the equivalent of the Linux ```Alt``` key is the ```option``` key. However, clicking ```option``` along with **_ANY character key_** will insert a special character into the string. In general ```Esc``` can be used in place of ``Alt`` on Macs_**.

Linux | &nbsp; Mac OS | Action
------ | ------ | ------
**```Alt D```** | &nbsp; **```Esc D```** | Delete all characters to end of line.
**```Alt B```** | &nbsp; **```Option <```** | Move cursor back one word on current line.
**```Alt F```** | &nbsp; **```Option >```** | Move cursor forward one word on current line.
**```Alt C```** | &nbsp; **```Esc C```** | Capitalize the character under the cursor.
**```Alt L```** | &nbsp; **```Esc L```** | Uncapitalize every character to the end of a word.
**```Alt U```** | &nbsp; **```Esc U```** | Capitalize every character to the end of a word.

## **_Controlling execution of prcesses running in the console_**.

Keys | Action
------- | ------
**```Ctrl C```** | Stop process currently running in the terminal.
**```Ctrl S```** | Hide all screen output from the currently running process.
**```Ctrl Q```** | Restart screen output from the currently running process.

## **_Miscellaneous helpers_**
Keys | Action
------- | ------
**```Tab```** | Autocomplete file and folder names relative to current directory.
**```Ctrl L```** | Clear all content from the visible screen. 

## **NOTE :** On a MAc, the ```option``` key is also the ```Alt``` key.

&nbsp;

## **_Reserved Command Line Characters_**
Character | Purpose
------ | ------
&nbsp; &nbsp; ```~``` | Shortcut to your home directory.
&nbsp; &nbsp; ```?``` | Wildcard. Allows for a match with **_ANY single character_** at that place in a string or command.
&nbsp; &nbsp; ```*``` | Wildcard. Allows for a match of **_ANY SET of multiple characters_** at that place in string. Especially useful when dealing with long file names.
&nbsp; &nbsp; ``` $ ``` | Print the value of a variable. For Example, ```$fubar``` would print the value of the variable named **fubar**. May be used in sripts to insert a variable's value into a string or as an argument to a command.
&nbsp; &nbsp; ```;``` | Used to separate multiple commands on a single line.
&nbsp; &nbsp; ```\``` | Backslash. Allows use of other reserved characters in strings and as arguments.
&nbsp; &nbsp; ```|``` | Send ( **_pipe_** ) output from one command as input to another command.
&nbsp; &nbsp; ```>``` | Redirect output from a command to a file. This will replace an existing file with the new output.
&nbsp; &nbsp; ```>>``` | Append output from a command to a file. If the file does not exist, it will be created.
&nbsp; &nbsp; ```<``` | Redirect output from one command as input to another command.
&nbsp; &nbsp; ```&``` | When included at end of a command, the command is executed as a background process.

## **_Reserved Command Closure Characters_**
Character | Purpose
------ | ------
&nbsp; &nbsp; ``` ' ' ``` | Single qoutes. Use string eaxcatly with no substitutions.
&nbsp; &nbsp; ``` " " ``` | Double quotes. String contructed with substitions allowed.
&nbsp; &nbsp; ``` ` ` ``` | Substitue output from enclosed command at this point.
&nbsp; &nbsp; ``` [ ] ``` | Conditionally match any of the characters included.
&nbsp; &nbsp; ``` ( ) ``` | Execute enclosed command in a subshell.

&nbsp;

## **_Also of interest_**
----------
###  [Bash documentation online](bashdocs.md)
###  [Bash for Windows](bashwin.md)