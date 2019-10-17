# Using the ECRL Anaconda scripts to manage environments on your personal computer

### _**These tools only work with Linux or Mac OS operating systems**_

## Setting up your tools

1. Download the Anaconda environement management scripts from https://github.com/ECRL-Cornell/myanaconda
>  * _**IGNORE the downloaded anaconda.sh file> IT MUST NEVER BE USED to manage environments on a desktop or personal computer !!**_

2. Install the downloaded _**conda_create**_ and _**install_miniconda**_ scripts into a directory in your PATH. 
> * Best practice would be to install the scripts in a _**bin**_ directory rooted in your home directory.
> > * If you don't already have a _**bin**_  directory, you can create one by typing ```mkdir ~/bin```  on the command line from your home directory. 
> > * If you had to create a new ```bin```  directory, you must add it to the list of directories in your ```PATH``` environemnt variable using ```export PATH=\$HOME/bin:$PATH``` 
> > * To have this new ```PATH``` set automatically each time you login, add the above ```export``` command to whichever of ```.bashrc``` or ```.profile**``` exists in your home directory.

3. Copy the donwloaded **myanaconda.sh** to your home directory the edit your ```.bashrc``` or ```.profile``` and add the following line to the bottom of the file.
> > ```source ~/myanaconda.sh```


# THERE NEEDS TO BE SEPARATE SCRIPT SETS FOR SEREVERS AND DESKTOPS !!!!!!


## Using **_conda_create_** on deesktops and personal computers

The **_conda_create_** script does the heavy lifting required to create a variety of new Anaconda Python environments. The original script is in 
**$ANACONDA_COMMON_ROOT/scripts/conda_create**, however sourcing anaconda.sh creates a bash alias to that locaton.

**Supported types of installs**
1. **_basic_** - this is the default. It will install the most basic set of packages required for a project. The default package list is read from the file **$ANACONDA_COMMON_ROOT/scripts/anaconda-base-pkgs.txt**. 

2. **_file_** - will read the list of packages to install from a file that you supply. The file may contain either simple text with one package name per line or entries in **YAML** format.
    > You can create a YAML file for this purpose from any activated environment using :
    * **conda env create --file environment.yml**

3. **_anaconda_** - will install the complete Anaconda distribution into the new environment. Beware, this environemnt has a large number of packages that most people will never use. And it will require as much as 5GB of disk space for Python 2 and 3GB for Python 3.

**Usage**

>**_conda_create_ [-a -h -f -p -s] -n _name-of-environment_ ...**
* REQUIRED arguments
    * **-n _name-of-environment_** &nbsp;&nbsp;:&nbsp;&nbsp;name for the new environment

* OPTIONAL arguments
    * **-a** &nbsp;&nbsp;:&nbsp;&nbsp;create a full Anaconda environment
    * **-h** &nbsp;&nbsp;:&nbsp;&nbsp;show help
    * **-f _path-to-file_** &nbsp;&nbsp;&nbsp;create an environment using packages specified in a file
    * **-p** &nbsp;&nbsp;:&nbsp;&nbsp;version of Python to install 
        * defaults to version found in the **PYTHON3_DEFAULT** environment variable
    * **-s** &nbsp;&nbsp;:&nbsp;&nbsp;environment is to be shared
        * by default, all environments are personal
        * you must have admin privileges to create shared environments
        * __NOTE__: the shared, full Anaconda environments **_anaconda2.7_** and **_anaconda3.6_** already exist on servers used by ECRL

* ... REQUIRED and OPTIONAL arguments may be followed by a space separated list of additonal packages to install


## Convenience Functions
> created when **anaconda.sh** is sourced

### **activate**
> replaces the standard **_source activate_** with options to manage activation of shared and personal envionments that are stored in different root directories
* activate a global (shared) environment 
    * **activate -s _env_name_**
* activate your own private environment
    * **activate _env_name_**
* activate another team member's private environment
    * **activate -p _env_name_**

### **deactivate**
* **_deactivate_** 
    * requires no arguments becuase it takes advantage of Anaconda's built-in environment variables to detect the currenty active environment.


## Environment Variables
Several environemnt variables specific to this toolset are created by the _anaconda.sh_ script. These environment variables are used by the utility scripts described in the next section.

**PYTHON2_DEFAULT** = 2.7
> Default version of Python to be used when creating new Python 2 environments.
      
**PYTHON3_DEFAULT** = 3.6
> Default version of Python to be used when creating new Python 3 environments.

**ANACONDA_COMMON_ROOT**
> Root directory where all Anaconda environments and scripts reside.

**ANACONDA_SHARED_ROOT**
> Directory where shared Anaconda environments are installed.

**ANACONDA_USERS_ROOT**
> Root directory where personal Anaconda environments are installed.

**MINICONDA2_DIRPATH**
> Direcotry where common Miniconda 2 is installed. **Minicoda2** is used by the scripts to create and manage Python 2 environments. 

**MINICONDA3_DIRPATH**
> Directory where shared Miniconda 3 is installed. **Minicoda3** is used by the scripts to create and manage Python 3 environments. 
