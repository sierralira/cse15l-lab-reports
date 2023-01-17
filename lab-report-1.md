## Lab Report 1
### Step 1: Installing VScode
To install Visual Studio Code, a user should go to the Visual Studio Code website, using the link [https://code.visualstudio.com](https://code.visualstudio.com/), then downlaod the version that corresponds to their operating system, macOS or Windows, and follow the prompted installation steps. I did not have to download Visual Studio Code as my prior enrollment in CSE8B had required me to download it at the beginning of the fall quarter. 
>![Image](lab-report-1-image-1.png)
### Step 2: Remotely Connecting
To remotely connect, a user must first install git, using the link [https://gitforwindows.org](https://gitforwindows.org/). Once git is installed, the Git Bash terminal should be set to the default terminal. Then, the line of code, `ssh cs15lwi23___@ieng6.ucsd.edu` with the blank being filled by the user's unique letter set in their account name, is used to access the remote server and the user is prompted to enter their password, note that although it will appear as though nothing is being typed, it is simply not visually apparent and the typed input is being received
>![Image](lab-report-1-image-2.png)
### Step 3: Trying Some Commands
The commands that I ran during my remote connection were `cd ~`, `cd`, `ls -lat`, `ls -a`, `ls /home/linux/ieng6/cs15lwi23/cs15lwi23abf`, cs15lwi23abf being the account of my lab partner, and `cp /home/linux/ieng6/cs15lwi23/public/hello.txt ~/`. `cd` causes the current directory to be changed and `cd ~` causes the current directory to be changed to the home directory. `ls -lat` lists the items in the directory and `ls -a` shows the hidden items in the directory. `ls /home/linux/ieng6/cs15lwi23/cs15lwi23abf` attempts to access the directory of another user, however I received a message that I did not have permission to access it. 
>![Image](lab-report-1-image-3.png)
