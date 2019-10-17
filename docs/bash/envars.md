# BASH Shell Envrionment Variables

### The Bash shell uses environment variables to persist important information from one session to another. 

### **Everything documented here works the same in both the Linux and Mac OS operating systems.**

## Here are some of the more useful environment variables set by the shell each time you log in.


| Variable | Value |
| ------- | ------- |
| ```HOME``` | the path to youy home directory |
| ```PATH``` | a list of all directories in the current full path |
| ```PWD``` | full path to the  current directory (```P```resent ```W```orking ```D```irectory) |
| ```USER``` and ```LOGNAME``` | the login ID of the curent user (```YOU !```) |
| ```SHELL``` | the name of the curreny |
| ```LANG``` | the language used in the shell, usually |**_en_US.UTF-8_** |
| ```CDPATH``` | not set by default, see [Using CDPATH](#using-cdpath) |

### **_```DO NOT EVER CHANGE```_ ```the values of HOME, PWD, USER, LOGNAME, SHELL or LANG !!```** The shell uses them extensively and relies on their values being correct as set by the operating system. 

```PATH``` is used by the shell whenever it searches for executable code. It's initial value is usually "```/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin```". You may occassionally need to add other directories to the system path. The discussion of the &nbsp;_```export```_&nbsp; command below has instructions on how to do this properly.

&nbsp;

-------
## Use the _```env```_ command to display a list of all current environment variables and their values.

>   \>\>  ```env```

* HOME=/Users/netid
* LANG=en_US.UTF-8
* PATH=/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin
* PS1=\h:\W \u\$
* SHELL=/bin/bash
* USER=netid
* ... along with every other variable name=value
* ... in alphabetical order on Mac OS, but not always on Linux.

&nbsp;

-------
## Use the _```echo```_ command along with the _```$```_ special to view the value of a single variable.

> \>\> ```echo $PATH```
* /usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin

&nbsp;

-------
## Use the _```export```_ command to create your own environment variables.
### This will come in especially handy when you want to carry over information from one session to another or make values available to any script that may run in the shell.

### Environment variables are most often used as shortcuts in paths to files. Convention is to use **ALL CAPS** for the names of environment variables. Separate words with a single &nbsp;```_```&nbsp; (underscore).

>   \>\>  ```export``` APPDATA_PATH="/Volumes/data"

>   \>\> ```cd $APPDATA_PATH/draught/2016```

### As previously mentioned, the ```PATH``` environment varible is used by the shell whenever it searches for executable code. You will occasionally find it necessary to add the path to your own scripts or other installed applications to the original ```PATH```. When you do so, always PREPEND the new directories to the original path using ```:``` (colons) between each new path.

### When setting a new value for ```PATH```, always use ```$PATH``` to refer to the original system path. This will make the code creating the new path compatible with any machine running Bash, regardless of the number or order of the system directories.

> \>\> ```export PATH=/full/path/to/scripts:/full/path/to/more/programs:$PATH```

&nbsp;

-------

## ```CDPATH```

### ```CDPATH``` does not have a default value. However, when set, the ```CDPATH``` environment variable extends the reach of the **```cd```** command to include the current directory **_plus all directories_** in ```CDPATH```. The rules for setting ```CDPATH``` are the same as those for ```PATH```.

### For example, this sequence of cpmmands :

> \>\> ```cd ~/data``` 

> \>\> ```export CDPATH=/data;/data2```

> \>\> ```cd cmip6``` 

Will find switch to the first occerence of a ```cmip6``` directory after searching first in ```$HOME/data```, then in ```/data``` and finally in ```/data2```.

