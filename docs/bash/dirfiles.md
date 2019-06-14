# Working with directories and files in a Bash.

ECRL tools are developed and run locally on servers and Mac OS computers. All of these computers are based on a version of Linux that uses the Bourne Again Shell (BASH). So a basic knowledge of shell commands for managing directories and files is important. 

### **Everything documented here works the same in both the Linux and Mac OS operating systems.**

&nbsp;

## **Use the **_```cd```_** command to navigate among directories.**
-------
### For example, go to the ```pyhome``` sub-directory of the current duirectory.
>   \>\> ```cd pyhome``` &nbsp; 

### ```$HOME```  is an environment variable that contains the path to your home driectory.

>   \>\> ```cd $HOME\code\myproject``` &nbsp; full path to the &nbsp;```myproject```&nbsp; directory in your home directory.

#### **HINT : _you don't have to type the full directory name_**. Just enter the first few _unique_ charcters, then press the ```TAB``` key to get the full name of the directory.

>   \>\> ```cd $HOME\code\myp``` &nbsp; &nbsp; _then press the  ```TAB``` key_

>   \>\> ```cd $HOME\code\myproject```

#### You may also use the &nbsp;```~```&nbsp; as a shortcut for ```$HOME```
>   \>\> ```cd ~\code\myproject```

>   \>\> ```cd ~```  &nbsp; _will return to your home directory_

>   \>\> ```cd``` &nbsp; &nbsp; _without any arguments is the easiest way to get to your home directory_.

### ```..``` can be used to move one directory up in the tree or jump among sub-directories.
#### For these examples, the ```code``` directory in $HOME has 2 sub-direcories named ```project1``` and ```project2```
>   \>\> ```cd ~\code\project1```

>   \>\> ```cd ../project2``` &nbsp; &nbsp; _will move you to the ```project2``` sub-directory of &nbsp;```~/code```_.

>   \>\> ```cd ..``` &nbsp; &nbsp; _will move you up to the &nbsp;```~/code``` directory_.


### _**WARNING**_ typing &nbsp;**_```man cd```_**&nbsp; in the command line will display very limited (and ultimately useless) information for all 100+ built-in Linux commands.

### **_For additional **```cd```** documentation read these [cd docs online](https://ss64.com/bash/cd.html)_**

&nbsp;

## **Use the **_```ls```_** command to list the contents of a directory.**
-------
### **For example, a software directory might look like this :**
>   \>\> ```ls```

    morecode       pyfunc1.pyc    pyfunc2.pyc
    pyfunc1.py     pyfunc2.py

### **To list files in the ```morecode``` subdirectory**

>   \>\> ```ls morecode```

    data1.nc
    data2.nc

### **List contents of any directory in the file system using it's full path.**

> \>\> ```ls /full/directory/path``` 
    
### **Use &nbsp;```ls```&nbsp; with the &nbsp;```-l```&nbsp; option to include key descriptive details.**

>  \>\> ```ls -l```

    -rw-r--r--   1 netid  ECRL Users      0 Jul  8  2015 __init__.py
    -rw-r--r--   1 netid  ECRL Users    153 Nov 26 15:40 __init__.pyc
    -rw-r--r--   1 netid  ECRL Users  15698 Apr  7  2018 config.py
    -rw-r--r--   1 netid  ECRL Users   8285 Jan  3 17:14 config.pyc
    drwxr-xr-x   4 netid  ECRL Users    136 Nov 26 14:52 docs
    -rw-r--r--   1 netid  ECRL Users   6036 Oct  2  2015 factory.py
    -rw-r--r--   1 netid  ECRL Users   5914 Nov 26 15:40 factory.pyc
    -rw-r--r--   1 netid  ECRL Users   4489 Sep  6  2017 grid.py
    -rw-r--r--   1 netid  ECRL Users   4388 Nov 26 15:40 grid.pyc

### **The first column shows type and permissions** for each entry in the list.  If the first character is  ```-```,  the item is a file. ```d``` indicates a directory. ```l``` indicates a link.

### **The next 9 digits contain triplets that define the item's access permissions.** Available permissions are indicated by 3 letters ```rwx``` (```R```ead, ```W```rite and e```X```ecute). Individual permissions are set for the Owner, Group and Others (world).

&nbsp;
<div align=center>
<image src="permissions-etc.png">
<div align=center>&copy; 2019 Derek Parsons and Rick Moore</div> 
</div>
&nbsp;

### **Descriptions for the remaining columns**

Column | Description
------ | ------
2 | 1 for files or number of items in a directory
3 | thw owner (for ECRL, their netid)
4 | a group with special access (in this case "ECRL Cornell")
5 | the actual size of the item in bytes
6 | the date the item was last modified
7 | the name of the item


### **File or directory names beginning with a period (```.```) are hidden from &nbsp;```ls```&nbsp; by default.** Use the &nbsp;**_```-a```_**&nbsp; option to display those "hidden" files.

> \>\> ```cd ~``` &nbsp; &nbsp; (go to your home directory)

> \>\> ```ls -a``` &nbsp; &nbsp; (list all items in directory)

    .                   .condarc          .vim
    ..                  .config           .viminfo
    .Trash              .gitconfig        .vimrc
    .bash_history       .ipython          .vscode
    .bash_profile       .jupyter          bin
    .bash_sessions      .matlab           Desktop
    .bashrc             .spyder2          Documents
    .conda              .ssh              Downloads

### The single period at the beginning in this listing is a reference to the current directory, while the double period is a reference to the parent directory. Everything else is an item in the current directory.

### **Use the ```-al``` options to add essential details to the listing.**
>  \>\> ```ls -al```

    drwxr-xr-x@  91 netid  ECRL Users   3094 Apr  2 10:45 .
    drwxr-xr-x   12 root   admin                   408 Oct 24 11:58 ..
    drwx------  263 netid  ECRL Users   8942 Apr  1 17:22 .Trash
    -rw-------    1 netid  ECRL Users  14909 Apr  1 16:31 .bash_history
    -rwxrwxr--    1 netid  ECRL Users    276 Jan 31 13:52 .bash_profile
    drwx------  109 netid  ECRL Users   3706 Apr  2 10:36 .bash_sessions
    -rw-r--r--    1 netid  ECRL Users   1195 Apr  1 14:40 .bashrc
    drwxr-xr-x    5 netid  ECRL Users    170 Feb 19 15:03 .conda
    -rw-r--r--    1 netid  ECRL Users      3 Nov 12 13:54 .condarc
    drwx------    9 netid  ECRL Users    306 Jan 29 12:03 .config
    -rw-r--r--    1 netid  ECRL Users    179 Aug 13  2018 .gitconfig
    drwxrwxr-x@   8 netid  ECRL Users    272 Nov  2 14:07 .ipython
    drwxr-xr-x    4 netid  ECRL Users    136 Sep 10  2015 .jupyter
    drwxr-xr-x    4 netid  ECRL Users    136 Nov  6 10:58 .matlab
    drwxrwxr-x@  25 netid  ECRL Users    850 Nov  6 10:58 .spyder2
    drwx------    9 netid  ECRL Users    306 Mar  4 11:50 .ssh
    drwxrwxr-x@   9 netid  ECRL Users    306 Mar 18 11:19 .vim
    -rw-------    1 netid  ECRL Users  30063 Apr  2 10:45 .viminfo
    -rwxrwxr--    1 netid  ECRL Users   5578 Aug 16  2017 .vimrc
    drwxr-xr-x    4 netid  ECRL Users    136 Jan  3  2018 .vscode
    drwxr-xr-x   28 netid  ECRL Users    952 Apr  1 17:17 bin
    drwx------+  54 netid  ECRL Users   1836 Mar 18 10:58 Desktop
    drwx------+  13 netid  ECRL Users    442 Jan 25 15:32 Documents
    drwx------+  46 netid  ECRL Users   1564 Apr  1 13:11 Downloads

### **_For detailed documentation of the &nbsp;```ls```&nbsp; command and all of it's options, use &nbsp;```man ls```&nbsp; or read the  [ls docs online](https://ss64.com/bash/ls.html)_**.

&nbsp;

# Use the &nbsp;**_```mkdir```_**&nbsp;  command to create a new directory

> \>\> ```mkdir ecrl```

### **```mkdir```  can also create a path with multiple directories**

> \>\> ```mkdir -p ecrl/spring/2019```

### **_For more detailed documentation of the &nbsp;```mkdir```&nbsp; command use  ```man mkdir```  or read the  [mkdir docs oline](https://ss64.com/bash/mkdir.html)_**
----------

# Use the &nbsp;**_```rmdir```_**&nbsp; command to remove a directory

> \>\> ```rmdir ecrl```

### **BEWARE : _if a directory is not empty, ```rmdir``` will remove all ot the files and directories that it contains._ Unlike using "Move to Trash" on a Mac, ```THIS CANNOT BE UNDONE !!```**

### As a result, the example above also **PERMANENTLY** deleted the &nbsp;```ecrl/spring/2019```&nbsp; and &nbsp;```ecrl/spring```&nbsp; directories we created earlier along with **```every other file and directory```** that might have been in &nbsp;```ecrl```&nbsp;. So it is good practice to double check to make sure there is nothing you want in the entire directory tree **BEFORE** using &nbsp;```rmdir```.

&nbsp;

## **Use &nbsp;_```cp```_&nbsp; to copy a file or directory from one directory to another.**
-------
### Copy a file from one directory to another directory.
#### Copy the file named &nbsp;```download_cmip5_file.py```&nbsp; from your development script directory to a production script directory.
> \>\> ```cp ~/dev/scripts/download_cmip5_file.py /builds/scripts```

&nbsp;

## **Use &nbsp;_```mv```_&nbsp; to move a file or directory from one directory to another.**
-------
### Move a data file from a download diectory to a permenanet directory
> \>\> ```mv ~/downloads/whatever.nc /data/cmip5/.....```

&nbsp;

## **Use &nbsp;_```cat```_&nbsp; to print the contents of a file to the terminal.**
-------
### **BE CAREFUL : Only use this on text or text-like files.** Using &nbsp;```cat```&nbsp; on binary files will send garbage to the terminal, some of which may be interpreted as executable commands. Rare, worst case potentital is to crash your system. 

> \>\> ```cat 2019-82750-44000-Anthracnose-Risk.json ```

> \>\>{"name":"anthrac","dates":{"seasonStart":[2019,3,1],"fcastEnd":[2019,5,14],"fcastStart":[2019,5,9],"lastValid":[2019,5,14]},"location":{"lon":-82.75,"lat":44.0},"data":[0,0,0,0,0,0,0,0,0,0,0,0,1,0,0,1,0,0,0,1,0,0,0,0,0,0,0,0,0,0,0,0,2,1,0,0,0,0,0,0,0,0,1,1,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,1,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0]}

&nbsp;

## **Use &nbsp;_```touch```_&nbsp; to create an empty file.**
-------
> \>\> ```touch fillmeuplater.txt```

&nbsp;

## **Use &nbsp;_```chmod```_&nbsp; and &nbsp;_```ls```_&nbsp; to manage file and directory permissions.**
-------
### **Use  ```ls -l```   to show current permissions**

    -rwxr-xr-x    1 netid  ECRL Users      0 Jan 19 12:59 file1.txt

### **Give write permission to all members of the ERCL Users gtoup**

> \>\> ```chmod g+w file1.txt```

> \>\> ```ls -l```

    -rwxrwxr-x    1 netid  ECRL Users      0 Jan 19 12:59 file1.txt

### **_BEWARE : giving write permission to another user or group also gives them ```DELETE``` permission !!_** 
### **_On the flip side, if the owner doesn't have write permission, they will not be able to make any changes to the file, ```including changes to permissions !!```_**

&nbsp;
<div align=center>
<image src="managing-permissions.png">
</div>
<div align=center>&copy; 2019 Derek Parsons</div> 
&nbsp;

### **_For complete documentation of the ```chmod``` command use ```man chmod``` or read the [chmod docs online](https://ss64.com/bash/chmod.html)._**

<div align=center>&copy; 2019 Rick Moore</div> 

