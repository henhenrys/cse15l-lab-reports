# How to Use Remote Access and Log In
Here I will show how to get into your remote access account, and the steps that are taken to get to that point. 
We will be using the virtual environment to store any files remotely and use those files for any project. In no time
you will be able to work from various locations while accessing files from another account.

## The CSE15L Account
First to be able to even use this virtual environment, we need an account to do so. Luckily being in CSE 15L, we have an account for you ready. 
All we need to do is access it

To find your account go to link: https://sdacs.ucsd.edu/~icc/index.php and log in using your UCSD account username, and PID.

Once you have logged in, you are prompted with this page, and once here click on the cs15lwi23XXX.

<img width="552" alt="image" src="https://user-images.githubusercontent.com/108485221/212535867-0f185645-7dd8-492b-993f-97276ddac485.png">

Once there, you are prompted to change password, press that, and log in again using you UCSD account username, and PID.

<img width="552" alt="image" src="https://user-images.githubusercontent.com/108485221/212535545-29e3e8a3-47d1-4bae-b19a-11140dc3e71e.png">

Once you have logged in, you will be prompted to change your password. For your current password, put your UCSD login password for that, 
and for new password, you should put the password you want for the remote account. It is also important to note that no part of your name is allowed
in you password, and make sure to change the *Change MyTritonLink password?* to **No**, as you do not want to change your TritonLink password, only your 
remote access account password. Once completing all of this, **DO NOT** press *Check Password* as it tends to fail instead. Instead press enter/return 
after typing in the confirm your password instead.

<img width="552" alt="image" src="https://user-images.githubusercontent.com/108485221/212536145-3d4f4ab8-9ef4-4fbe-8466-447d1c31b13c.png"> 

Once you have completed all of this, you have successfully changed your account password and one step ready to begin. Keep in mind, the password change
will not take affect immediately, and will take some time before it goes into effect. So wait about 15-60 minutes before trying to log in. 

## Visual Studio Code
Many people will have some sort of IDE installed, whether it be VS code or something else, it will still work. If you do have VS Code or any other IDE skip
this and move onto the next step. Otherwise stick around. First, go to https://code.visualstudio.com/download. There you can select a specific download, 
based upon your operating system. 

<img width="552" alt="Screen Shot 2023-01-15 at 2 57 51 AM" src="https://user-images.githubusercontent.com/108485221/212536732-518d402e-b125-4be8-b633-10215d6214be.png"> 

Once you have downloaded the VS code, open up the zip file you have downloaded, and let that download VS code onto your machine.

<img width="552" alt="image" src="https://user-images.githubusercontent.com/108485221/212536850-20a6786e-f132-4799-8028-c58dcba53a1b.png">

Once all of this has been done, you should be able to open up VS code and now you have successfully installed an IDE by the name of Visual Studio Code.

<img width="552" alt="image" src="https://user-images.githubusercontent.com/108485221/212536943-bd98a120-8f4a-43aa-9b77-521d3ae3b56f.png">

## Remotely Connecting to Account
A lot of what is next will involve using the terminal to get access to our remote account. We will be using git commands along the way as well, and as
a result we need Git as well. Natively on Mac and Linux based machines, git is typically already on you computer and nothing needs to be done. But on Windows,
we will need to install that. To install use this link: https://gitforwindows.org/ and once installed open a new terminal in VS Code.

<img width="552" alt="image" src="https://user-images.githubusercontent.com/108485221/212537281-ca8dfa2d-3285-4cdf-a283-5bc036e7e331.png">

Once here, we would type in "***ssh cs15lwi23XXX@ieng6.ucsd.edu***". As it will be your first time logging in on your machine, it will ask if you  
"**Are you sure you want to continue connecting(yes/no/[fingerprint])?**" In which you should type into the terminal **yes**. Then it will ask for a password.
This is where the password you had made earlier will come into affect. Type in you password(*Even if it seems like nothing is being typed into the terminal
it is there, it is just not showing it*).

<img width="552" alt="image" src="https://user-images.githubusercontent.com/108485221/212537680-5e6db52d-6f5d-4cb1-bbb8-39c53a4a5028.png"> 

Once you have done everything you should get to a similar point to above. If you do see something similar, congratulations you have successfully accessed
your remote account.

## Trying Commands
There are many commands that you can do while in here. 

### From: 
* ls
* cd
* ls -a
* cp
* cat
* And many more
All of these comands all do something unique in their own way. Like how ls, lists out all the files present in the current directory. cd is changing
directories where you can go from one file to another. ls -a is to all possible directories in the current directory. cp is just copying something into
another file. And cat is just to essentially print out whatever is present in the file into the terminal.

<img width="552" alt="image" src="https://user-images.githubusercontent.com/108485221/212538363-db19c859-864b-4ae4-9c17-8a4df482f1d4.png"> 

## Closing Thoughts
This is everything one needs to know on how to access our remote accounts. Not everything shown will be a one to one into how one might do it as all of our
machines are different. And much the same can be said about us as a whole.We all have different working conditions, where some like to work in the comfort 
of the dorm, or even in the actual computer lab, being able to access these files remotely allows us to work whenever and however we would like to. Being 
to access and use these remote accounts will allow us to be more efficient with our time and make sure that we are successful being in CSE 15L.
