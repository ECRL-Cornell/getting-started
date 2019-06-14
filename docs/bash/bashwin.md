
## **Linux distributions for Microsoft Windows 10 or later**

### As of Windows 10, Windows has a subsytem that allows installation of a fast, fully functional Linux environment using Microsift's PowerShell tools. This includes most Linux commands, utilities and standard applications. It will also allow you to run your Linux-compiled apps directly in Windows.

### The Microsoft Store has complete distributions for Ubuntu, SUSE, Debian and Kali Linux 

### See Microsoft's [Windows Subsystem for Linux Documentation](https://docs.microsoft.com/en-us/windows/wsl/about) for details.

-------
&nbsp;
## **GNU Linux terminal and bash shell for Microsoft prior to Windows 10**

### One way is to install a Windows virtual machine manager and then set up a Linux virtual machine. ```We do not recommend this option``` because, historically, free virtual machines are inefficient wrappers that adversely affect the host computer's performance both within the Linux envirobnment and the native Windows OS. While commercial virtual machine managers are more performant, the cost is rarely worth it.

### **```CYGWIN```** is the preferred way to use Linux/Bash on a computer running Windows prior to version 10.

### **CYGWIN IS** a self-contained collection of GNU and other open source tools that provide a performant bash-like environment for Windows that is _similar to_ native Linux.
### **CYGWIN**
-   has access to all directories and files on a Windows computer
-   consists of code compiled for Windows, so it can be used to run most Windows applications
-   will work with a Windows distribution of ```Anaconda Python```

### **CYGWIN IS NOT** a way to run applications from a native Linux OS distribution on Windows.

### What this means :

-   Compiled programs from a Linux computer **_will not work_** in Cygwin
-   Scripts written using Bash can be run on Windows inside a Cygwin terminal provided they don't require accessto programs compiled for Linux.

### Cygwin documentation

-   [Cygwin home page](https://www.cygwin.com)
-   [Cygwin User Guide](https://www.cygwin.com/cygwin-ug-net.html)
-   [Cygwin API Reference](https://www.cygwin.com/cygwin-api)
-   [Cygwin Frequently Asked Questions](https://www.cygwin.com/faq.html)

### The absolute best description available is [Cygwin on Wikipedia](https://en.m.wikipedia.org/wiki/Cygwin)

