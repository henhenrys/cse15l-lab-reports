# Tasks performed in the Competition
During Week 7, we held a ccompetition in which we would comptete with one another in seeing who could perform the given tasks the fastest. Essentially, we would be using all the we have learned, and make use of time saving commands to save time when comleteing the various tasks. Personally, I did not win the competition, and was nowhere near as fast as the fastest, it was fun and this was what I had done during the competition.
## Goal of the Tasks Performed
In the given GitHub repository that we are using for this competition, It will contain a main file and a tester file as well. There is a bug within the main file where when we run the tester, it will fail. As a result, we will have to edit the file within the terminal and test the file again to see that it has fixed the bug. Afterwards we would commit and push the repository that we forked from GitHub, back to GitHub. Overall, this will test our ability to properly use commands line arguments effectively and efficiently. And assuming we have already done setup tasks 1-3, we will begin the timer.
### Step 4 - Log into ieng6
<img width="498" alt="Screen Shot 2023-02-26 at 10 41 58 PM" src="https://user-images.githubusercontent.com/108485221/221492678-092a4d1e-030e-49d9-8533-66362ead4c4a.png">

First logging into our ieng6 account is what we will do first. As normal, to log into the account, I used
```
$ ssh cs15lwi23XXX@ieng6.ucsd.edu <enter>
```
to log into my account as enter enables the terminal to run the command. As I have already set up a ssh key for my local machine to log into my remote account, I have no need to type in my password at all, and will intantly be logged into my remote account. 
### Step 5 - Clone Repository
<img width="405" alt="Screen Shot 2023-02-26 at 11 54 05 PM" src="https://user-images.githubusercontent.com/108485221/221505495-0f05aec4-4ca7-4ad5-98f1-3e03d6623434.png">

<img width="715" alt="Screen Shot 2023-02-26 at 11 07 32 PM" src="https://user-images.githubusercontent.com/108485221/221496925-4d2ead2b-b6c5-4623-849f-9d46d6a3897a.png">

Since I have also able to link my GitHub to my remote account using another ssh key, I could use the ssh on GitHub to also clone it into my remote account. I also use the ssh link given in GitHub to clone, as it is easier to overall send commit and push things back into my repository and it is the more secure way of cloning something as well. With this in mind, I did
```
$ git clone <ssh link from GitHub> <enter>
```
and then the process of cloning the repository will begin as enter is the key for the terminal to run the command. And once everything is done, the repository will be successfully cloned into my remote account, and since I cloned it using an ssh, it will be easier to commit and push back since the remote account is recognized as safe.
### Step 6 - Run Tests
<img width="972" alt="image" src="https://user-images.githubusercontent.com/108485221/221497895-f0810b54-28a8-4193-8d4d-74fda068e0b8.png">

In this step, we expected a failure, but we will need to compile everything in the directory and test them. But first I needed to get into the correct directory so I performed
```
$ cd la<tab>
```
to change into the correct directory. I also used `<tab>` there as I know that weren't anymore files similarly named in my root directory, the tab will autofill the directory and as a result save time.
Afterwards,I first copied the 
```
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
```
command from the webpage, and used that in my terminal by doing
```
$ javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java <enter>
```
where this will compile the all the java files for testing, and enter will tell the terminal to run the command in the command line.
Then afterwards, I copied the command
```
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore
```
and I had pasted and ran it through
```
$ java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests <enter>
```
where I was able to run the tests that was in the tester on the ListExamples.java file, and enter will execute the commmand and allow for the tests to run. Once the command goes to run, the result of
``` 
JUnit version 4.13.2
..E
Time: 0.52
There was 1 failure:
1) testMerge2(ListExamplesTests)
org.junit.runners.model.TestTimedOutException: test timed out after 500 milliseconds
        at ListExamples.merge(ListExamples.java:43)
        at ListExamplesTests.testMerge2(ListExamplesTests.java:19)

FAILURES!!!
Tests run: 2,  Failures: 1
```
should come out saying how one of our tests failed, and 1 passed.
### Step 7 - Edit Code
Since we know that there were fails with the test, we want to edit the file where there are errors. We can do
```
$ nano ListExamples.java
```
where we can open a text editor in my terminal to make edits in the ListExamples.java file. Once that has been perform, a window like this will appear.

<img width="505" alt="Screen Shot 2023-02-26 at 11 14 10 PM" src="https://user-images.githubusercontent.com/108485221/221498143-662d47b9-304a-4b2d-b7f2-3af6ceb5ee1c.png">

Once we have gotten here, we can make edits into the file where I pressed the keys

```
<down><down><down><down><down><down><down><down><down><down><down>
<down><down><down><down><down><down><down><down><down><down><down>
<down><down><down><down><down><down><down><down><down><down><down>
<down><down><down><down><down><down><down><down><down><right><right>
<right><right><right><right><right><right><right><right><right><right><delete><2>
```

which would get me this

<img width="505" alt="image" src="https://user-images.githubusercontent.com/108485221/221498626-694761f4-2385-4a1e-9758-340b219915a2.png">

As we cannot use our mouse to do any sort of edits, I am using the arrow keys to move aroound in the file. When we look at the failure reason originally, it gave us a line, so I kept pressing down arrow to get down to the same line that the error occured, and which would notice that the incrementation is wrong, so I moved right by pressing the right arrow, and go one extra space after we hover over the 1 that was a part of index1 and delete and change it to index2.
As we made changes we want to save it, so I performed

```
ctrl+o  <enter>  ctrl+x
```

in order to save the changes that I had made to the files and exit out of the nano text editor as well. The commands I had performed were to save and exit, where `ctrl+o` was used to write the changes to the file, and doing `<enter>` would save the changes into the file. Afterwards, `ctrl+x` would be used to get out of the nano text editor and we would return back to this

<img width="893" alt="Screen Shot 2023-02-26 at 11 15 08 PM" src="https://user-images.githubusercontent.com/108485221/221498281-1cf03e8c-b2cd-4ed5-bc64-c26021ce49a9.png">

### Step 8 - Rerun Tests
<img width="976" alt="Screen Shot 2023-02-26 at 11 18 45 PM" src="https://user-images.githubusercontent.com/108485221/221498897-9f7056b5-80b9-4b28-969f-26f9385c5d02.png">

Since we want to rerun the test and verify that the ListExamples.java file is properly functioning, we would recompile the file and rerun the tests. 
As I already ran the test beforehand, and also compiled it previously also, I can also use the same commands to do that. As a result I pressed the keys

```
<up><up><up><enter>
```

and that would bring up the 

```
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
```

and will run that command and recompile all the `.java` files. Afterwards, I needed to verify that the changes worked, so I would rerun the tester earlier by pressing the keys 

```
<up><up><up><enter>
```

and that would get me to the command

```
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests <enter>
```

and in getting this, when we run this command, we will be able to rerun the tester again with the newly compiled file. As a result of this, we would get

```
JUnit version 4.13.2
..
Time: 0.018

OK (2 tests)
```

This as a whole proves that the changes were sufficient in making it so the `ListExamples.java` file is correctly implemented.
### Step 9 - Commit and Push to GitHub
<img width="500" alt="Screen Shot 2023-02-26 at 11 19 45 PM" src="https://user-images.githubusercontent.com/108485221/221499074-b0c51918-fcd1-46e0-8e24-1945576cdaeb.png">

Now that we know that the file is working properly, we can commit and push the file into the github repository. 
First I typed out

```
$ git add *
```

which essentially will select all the files in the current directly that will be used in some sort of git command.
Then after, I go to type out
```
$ git commit -m "<message>"
```

which will take essentially a snapshot of all the changes that were made to the file and the message that was left after the changes that were made.
Since I have selected everything that will be changed, it is now time to foward that changes into my repository on GitHub. Here, I typed out

```
$ git push
```

which will send the commits and all the changes into the repository. And since I used a ssh link initially to do this, I bypass the verifcation process and can send it right to my repository, and as a result the commit has been done and the result is this.

<img width="893" alt="Screen Shot 2023-02-26 at 11 20 12 PM" src="https://user-images.githubusercontent.com/108485221/221499170-43a8ff2d-0540-4f39-a606-0f8741cbaf86.png">
## Conclusion
Although I wasn't able to compete with the likes of those who made it to the finals in terms of speed, I still learned a lot through this process. I was able to develop more skills into editting files and doing automation, where I wouldn't need to type my password every again, and much more. This did teach me to be more aware of other ways to efficiently save time in the coding/testing process. At the end, I did not win, I was fairly slow in doing this that I had no chance against those using bash scripts and etc. But overall, it was a nice way to see other people's way of thought and see ways in which I can improve myself in speeding up the coding/testing process and overall getting a better understanding of everything I do.
