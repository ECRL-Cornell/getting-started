# Bash Shell Programming

### Practical guildelines for developing Bash shell scripts.

&nbsp;

-------
## **_Script Argument Variables_**
Character | Purpose
------ | ------
&nbsp; &nbsp; ``` $# ``` | Number of positional parameters pased to the script.
&nbsp; &nbsp; ``` $- ``` | Number of option (hyphen) flags passed.
&nbsp; &nbsp; ``` $@ ``` | Ordered list of all positional paramaters passed to the script.
&nbsp; &nbsp; ``` $_ ``` | Absolute filename fo the script.
&nbsp; &nbsp; ``` $0 ``` | Get name of the script from within the script while it is executing.
&nbsp; &nbsp; ``` $$ ``` | ProcessID the bash shell.
&nbsp; &nbsp; ``` $! ``` | ProcessID of most recently executed background process.
&nbsp; &nbsp; ``` $? ``` | Get exit code of most recently executed foreground command.
&nbsp;

-------
## **_Reserved Command Closure Characters_**
Character | Purpose
------ | ------
&nbsp; &nbsp; ``` ' ' ``` | Single qoutes. Use string eaxcatly with no substitutions.
&nbsp; &nbsp; ``` " " ``` | Double quotes. String contructed with substitions allowed.
&nbsp; &nbsp; ``` ` ` ``` | Substitue output from enclosed command at this point.
&nbsp; &nbsp; ``` [ ] ``` | Conditionally match any of the characters included.
&nbsp; &nbsp; ``` ( ) ``` | Execute enclosed command in a subshell
&nbsp;

-------
## **_Also of interest_**
### [bash scripting cheetsheet](https://devhints.io/bash)
