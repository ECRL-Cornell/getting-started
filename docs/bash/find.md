# **How to search for content in a directory**

### **Everything documented here works the same in both the Linux and Mac OS operating systems.**

### The ```find``` command will search a directory or list of directories for items that match a name or pattern.

| Option | Argument | Action |
| ------ | ------ | ------ | 
| ```-name``` | "_pattern_" | Find all files with _```pattern```_ in the name. |
| | | Specifiy a full filename or use wilcard characters. Case matters !!|
| | | ```*```, ```?``` or ```[ ]``` wildcards are valid in the ```-name```. |
| ```-iname``` | "_pattern_" | same as ```-name``` but ignores case. |
| ```-print``` | | Print the results of the search to standard out. |
| ```-group``` | "_name_" | Find all files belonging to the _```name```_ group. |
| ```-amin```| _num_ | Find all files accessed in the previous ```num``` minutes |
| ```-cmin```| _num_ | Find all files created or changed in the previous ```num``` minutes |
 | ```-mtime``` | _days_ | Find all files that were modified a number of _```days```_ ago. |
| ```-newer``` | "_pattern_" | Find all files that were modified later than the one in _```pattern```_. |
| | | Uses the same wilcard rules as ```-name```. |
| ```-size``` | _num_ | Find all files with size == _```num```_ blocks. |
|  | _num**c**_ | Find files with size == _```num```_ bytes (_```num```_ characters for text files). |
| ```-type``` | _filetype_ | Find all files of the specfied type. |
| | **Type** | **Description** |
| | ``` b ``` | Block Device files (binary block access device driver) |
| | ``` c ``` | Character Device files (unbuffered, direct access device drivers)|
| | ``` d ``` | Directories |
| | ``` f ``` | Ordinary files (text, executable binaries, program data, etc. |
| | ``` l ``` | Symbolic links (i.e. a link from one place to a file in another place.) |
| | ``` p ``` | Named pipe files that can be read from or written to by |
| | | multiple processes. ```FIFO``` special files are most commonly used
| | |( ```F```irst ```I```n, ```F```irst ```O```ut ) |
| ```-maxdepth``` | _num_ | Limit search to the first ```_num_``` directories. |
| | | Use ```-maxdepth 1``` to search only in current directory. |

## **NOTES**
----------
### The &nbsp; ```-name``` &nbsp; and &nbsp; ```-type``` &nbsp; options may be combined in a single &nbsp; ```find``` &nbsp; command. For example :**
-   _**```find ./venvs -type d -name "code"```**_ &nbsp; would return a listing of all directories named ```code``` found in the ```./venvs``` directory or any of it's sub-directories.

### The &nbsp; ```-mtime``` &nbsp; option may be used twice in the same request to impose a range of days.
-   _**```find . -mtime +10 -mtime -20```**_ &nbsp; would find all files more than 10 days old but less tha 20 days old.

### The &nbsp; ```-size``` &nbsp; option may be used twice in the same request to impose a range of sizes.
-   _**```find . -size +10 -size -20```**_ &nbsp; would find all files more than 10 MB but less tha 20 MB.

&nbsp;

# **Wildcard characters**

### **Wildcard characters and their effects in the ```-name``` and ```-newer``` options.**
 
| Character | Description and results |
| ------ | ------ | ------ |
| &nbsp; &nbsp; ```*``` | represents any sequence of characters. For example :|
| | ```find "*.py"``` paths to all Python code files |
| | ```find "drought*.nc"``` paths to all NetCdf files that start with ```drought```. |
| | ```"find "*drought.nc"``` paths to all NetCdf files that end with ```drought```. |
| | ```find "*drought*.nc"``` paths to all NetCdf files with ```drought``` anywhere in the name. |
| | ```find "*drought*.*"``` paths to any type of file with ```drought``` anywhere in the name. |
| &nbsp; &nbsp; ```?``` | represents any single character. For example : |
| | ```find "?.py"``` paths to all Python code files that have a single letter name.|
| | ```find "precip?.nc"``` paths to all NetCdf files named ```precip``` plus any single character. |
| | ```find "?precip.nc"``` paths to all NetCdf files that start with any character and end with ```precip```. |
| | ```find "?precip?.*"``` paths to all NetCdf files that with ```precip``` bracketed by any other single characers. |
| &nbsp; &nbsp; ```[ ]``` | represents a list or range of **_```individual```_** characters or numbers.
| | using  ```[ ]``` with a range of values : |
| | ```find "script[2-4].sh"``` paths to &nbsp;_script2.sh_, &nbsp;_script3.sh_ &nbsp;and/or &nbsp;_script4.sh_ |
| | ```find "[x-z]script.sh"``` paths to &nbsp;_xscript.sh_, &nbsp;_yscript.sh_ &nbsp;and/or &nbsp;_zscript.sh_ |
| | using  ```[ ]``` with a list of values : |
| | ```find "script[135].sh"``` paths to &nbsp;_script1.sh_, &nbsp;_script3.sh_ &nbsp;and/or &nbsp;_script5.sh_ |
| | ```find "[aft]script.sh"``` paths to &nbsp;_ascript.sh_, &nbsp;_fscript.sh_ &nbsp;and &nbsp;_tscript.sh_ |
| | mixing a list of values and a range of values : |
| | ```find model[ev]/run[1-3].nc"``` paths to NetCdf files for runs 1, 2 and/or 3 of models e and/or v.| 
