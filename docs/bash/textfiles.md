# Exploring and manipulating content of text files from the BASH command line.

ECRL tools are developed and run locally on Linux servers and Mac OS computers. All of these computers are based on a version of Linux that uses the Bourne Again Shell (BASH). So a basic knowledge of shell commands for exploring and manipulating file content is important. 

### **Unless other wise noted, everything documented here works the same on both the Linux and Mac OS operating systems.**

&nbsp;

# Tools for viewing file content.


## **Use _```head```_  to view the first few lines in a file.**
-------

### The default is to display the first 10 lines of the file.

> \>\> ```head anything.py```

 ### Use &nbsp;```-n```&nbsp; followed by a number to see more or fewer lines.

> \>\> ```head -n 20 anything.py```

- shows the first 20 lines

&nbsp;

## **Use _```tail```_ to view the last few lines in a file.**
-------`

### The default is to display the last 10 lines of the file. 

> \>\> ```tail anything.py```

### Use &nbsp;```-n```&nbsp; followed by a number to see more or fewer lines.

> \>\> ```tail -n 20 anything.py```

- shows the last 20 lines

&nbsp;

## **Use  &nbsp;_```less```_&nbsp; to page forward &nbsp;_and backward_&nbsp; through a file's content.**
-------

### **```less``` displays a file's content from the first line through the last line, one seguence of lines at a time**

- press either  &nbsp;```<space>```&nbsp; or &nbsp;```<page down>```&nbsp; to scroll forward one page.

- press &nbsp;```<return>```&nbsp; to scroll forward one line.

- press  &nbsp;```<page up>```&nbsp; to scrool back to the previous page.

- press &nbsp;```q```&nbsp; at any time to quit. **```less```&nbsp; will never quit by itself**, so even at the end of the file, you must press &nbsp;```q```&nbsp; to quit.

### **For example, assume the file contains 100 lines and your terminal has 40 lines**.

> \>\> ```less anything.py```

 -  scrolling forward will display lines 1 thru 40, then lines 41 thru 80 then lines 81 thru 100. 

### **Use the &nbsp;```-c```&nbsp; option to clear everything from the screen before showing the file's content**

> \>\> ```less -c anything.py```

### **Change the scroll rate.**

- use a number followed immediately by &nbsp;```d```&nbsp; to scroll down N lines.

- use a number followed immediateby &nbsp;```u```&nbsp; to scroll up N lines. 

- once a  number of lines is set by either ```d``` or ```u```, each subsequent scroll in either direction will use that number of lines. This setting also affects the behavior of the &nbsp;```<space>```&nbsp;, &nbsp;```<page up>```&nbsp; and &nbsp;```<page down>```&nbsp; keys.

### **Use the &nbsp;```-N```&nbsp; opition to display line numbers.**

> \>\> ```less -N anything.py```

### **```less```&nbsp; is very flexible with 50+ options and key functions. Use &nbsp;```man less```&nbsp; to discover what else it can do.**

### This [LifeWire page](https://www.lifewire.com/what-to-know-less-command-4051972) has a very good explanation of ```less``` with many practicle examples.

&nbsp;

## **Use the &nbsp;_```more```_&nbsp; command to scroll through a file's content.**
-------
> \>\> ```more anything.py```

### **On Mac OS, &nbsp;```more```&nbsp; is an alias for &nbsp;```less```&nbsp;, so the &nbsp;```less```&nbsp; documentation and examples above apply.**

### **On Linux servers, &nbsp;```more```&nbsp; scrolls forward through a file's content from the first line to the last line, ```There is no scrolling backwards```.**

### **```more```&nbsp; has very few options on Linux.**

- use &nbsp;```<space>```&nbsp; or &nbsp;```<page down>```&nbsp; key to scroll ahead one screen.

- use &nbsp;```<return>```&nbsp; to scroll ahead 1 line.

- use &nbsp;```-NUM n``` &nbsp;to show &nbsp;**```n```**&nbsp; lines per screen

- use &nbsp;```+NUM n``` &nbsp;display file beginning with line number &nbsp;**```n```**

- press &nbsp;```q```&nbsp; at any time to quit.

### **On Linux, ```more``` will quit automatically at the end of the file.**

&nbsp;

## **Use the _```cat```_ command to dump content of a file or multiple files to standard out.**
-------
### **NOTE: when ```cat``` ouput is sent to the terminal, files are displayed _without paging_**.
### **Display contents of a file in the terminal**.

> \>\> ```cat retrieve.py```

- writes the entire contents of the file to the terminal.

### Use the &nbsp;```-n```&nbsp; option show line numbers

> \>\> ```cat -n retrieve.py```

- writes the contents of &nbsp;```retrieve.py```&nbsp; to the terminal with the content of each line preceded by a line number. 

### **Use &nbsp;```>```&nbsp; to merge 2 files into a single new file**.

> \>\> ```cat retrieve.py plot.py > retriece_and_plot.py```

- writes the contents of &nbsp;```retrieve.py```&nbsp; to the file named &nbsp;```retriece_and_plot.py```&nbsp;, then append the contets of &nbsp;```plot.py```.
-  **CAUTION :** &nbsp;if ```retriece_and_plot.py```&nbsp; existed prior to this command, it will be overwritten and &nbsp;**_```cannot be undone```_**.

### **Use &nbsp;```>>```&nbsp; to aoppend a file to the end of an existing file**.

> \>\> ```cat file3.txt >> muutiple_files.txt```


&nbsp;

## **Use the _```diff```_ command to find the differences between 2 files.**
-------

> \>\> ```diff plot.py plot.py~```

will display the differences between the 2 versions of ```plot.py```

- use the &nbsp;```-i```&nbsp; option to ignore differences in case between files

- use the &nbsp;```-b```&nbsp; option to ignore differences in amount of white space

- use the &nbsp;```-B```&nbsp; option to ignore all blank lines

- use the &nbsp;```-i```&nbsp; option to ignore differences in case between files

- use the &nbsp;```-E```&nbsp; option to ignore differences in tab expansion

- use the &nbsp;```-w```&nbsp; option to ignore all white space

### Use &nbsp;```man diff```&nbsp; to see all 30+ options.

&nbsp;

## **Use the _```wc```_ command to get number of lines, words and characters in a file.**
-------

### Default is to count the number of lines, words and characters

> \>\> ```wc anthrac.py```

&nbsp; &nbsp; &nbsp; &nbsp; 171  &nbsp; &nbsp; 973 &nbsp; &nbsp; 7320 &nbsp; &nbsp;anthrac.py


- use the &nbsp;```-l```&nbsp; option to count only the number of lines in a file.

- use the &nbsp;```-w```&nbsp; option to count only the number of words in a file.

- use the &nbsp;```-c```&nbsp; option to count only the number of characters in a file.

&nbsp;

## **Use the _```sort```_ command sorts the content of text files line by line and writes sorted content to standard ouput.**

### **Sort can be used on a single file or to sort and concatenate a group of files.**
-------

- use the &nbsp;```-f```&nbsp; option to fold (i.e. ignore) case. 

- use the &nbsp;```-d```&nbsp; option consider only blanks and alphanumeric characters

- use the &nbsp;```-m```&nbsp; option to 

- use the &nbsp;```-m```&nbsp; option to merge previously sorted files. 
