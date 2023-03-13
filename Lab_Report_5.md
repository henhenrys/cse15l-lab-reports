# Finishing Lab 6
I actually really enjoyed my time working on lab6. I was actually really fond of actually working on bash scripts, and also understanding how grades are calculated behind the scenes in gradescope. So as a result of that, I decided I want to continue to work on it, to function and work for most/all of the repositories that were present in the lab 6 assignment.

## The Actual Code Itself
In general, results don't matter if you don't understand the code, but, as the writer of the code I do understand, and this is my code for it
```
CPATH='.:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar'

rm -rf student-submission
rm -f ListExamples.*
git clone $1 student-submission
echo 'Finished cloning'
cd student-submission

if [[ -f ListExamples.java ]]
    then
        echo "ListExamples found"
    else 
        ls
        find ./ -name "ListExamples.java" > findListExamples.txt
        cat findListExamples.txt
        findListExample=`grep "ListExamples" findListExamples.txt`
        echo $findListExample
        result=($(wc -c < findListExamples.txt))
        PASSED=$(echo "($result-21)" | bc)
        results=${findListExample: 3: $PASSED}
        echo $results
        cd "${results}"
        if [[ -f ListExamples.java ]]
            then
                echo "ListExamples found"
                cp ListExamples.java ..
                cd ..
            else 
            echo "Error: ListExamples not found"
            echo ""
            echo "--------------"
            echo "| Score: 0/1 |"
            echo "--------------"
            echo ""
            exit 1
        fi
    fi
cp ListExamples.java ..
cd ..
set +e
javac -cp $CPATH *.java
if [[ $? -ne 0 ]]
then
    echo ""
    echo "Error: Compile Error"
    echo ""
    echo "--------------"
    echo "| Score: 0/1 |"
    echo "--------------"
    echo ""
else
    java -cp $CPATH org.junit.runner.JUnitCore TestListExamples > result.txt
    java -cp $CPATH org.junit.runner.JUnitCore TestListExamples | grep -i "Test" > failure.txt
    result=($(wc -w < failure.txt))
    if [[ $result == 3 ]]
    then
        echo ""
        echo "All tests passed"
        echo ""
        echo "--------------"
        echo "| Score: 1/1 |"
        echo "--------------"
        echo ""
    else
        cat result.txt
        echo ""
        echo "--------------"
        echo "| Score: 0/1 |"
        echo "--------------"
        echo ""
    fi

fi
```

Since, we already know that, in the tester, there is only one test, if there were to be any point of failure, that means the score would be a 0/1 as a result and 1/1 is if was all correct. 

At the very beginning of the script, it is simple procedure in cloning the repository into the directory and then having it look for the desired file, `ListExamples.java`. Here I just made sure to check if it has it right away, but if that fails, I would use the find command and look through everywhere for an exact match of paths that could lead to `ListExamples.java` file. And then I editted it to make sure to only get the necessary path to get to said directory and check again if it is there or not. Here it will determine whether or not the file is there or not. I made use of my new found knowledge in the find command, and used Shell Parameter expansion that I recently learned from the write up on the newest Skill-Demo-2.

Right after we have everything copied in the main directory that we would be working in, and there we start to compile everything we need. There after, we check if there was anything that had resulted while compiling, and if so, it would be easy to deduct a compile error as a result.

At the very end, we start to assign grades from the results. I want to have a copy of the result at hand, so I ran the tests and had them be put into the file of `result.txt` for use later. I also ran the tests again, and had only the line that contained "Test" in it and had it be put into `failure.txt`, for use of comparison at a later point. With that, I ended up trying the find the total amount of words in the `failure.txt` file. Afterwards, I checked if the total words was 3, as in a passed test, there will only be 3 words in the same line as "Tests", and so it would be easy to see that, that file passed. However, if that wasn't the case, then that means their implementation failed as a result, so I had it print out the fail to see what was failing, and gave a grade of a 0/1 also. Here, I also made use of my new found knwoledge in using `grep` most effectively and making use of commands like `wc` to get word count as well.

Right after are some test cases on some of the GitHub repositories and results from my implementation

## Code from Starter in Week 3
We know that in week 3, we had also done something in regards to ListExamples, and from lab 3, we also know the implementation is incorrect in lab 3. In such, we know that the result of this would be a fail, but not a compile error, as there is no errors besides implementation, nor a non-existent file, as the file name is properly named.

<img width="826" alt="image" src="https://user-images.githubusercontent.com/108485221/224667881-2eb64131-9fc2-489d-8986-61ede329db4d.png">

As we can see here, everything was perfected fine with the file. There was no compiling issues at all, and the file was recognized and found. But, we see that there was a problem with the code itself, as it failed a test case in the tester, and as a result failed as well.

This result was exactly what was expected and no problems occured with the script in running and executing it correctly.

## Code that was Corrected
Since we know the following code has been corrected, there is no reason not to think that the would be any problems. As a result, it is expected that there would be no compile issues, no file header issues, and no implementation issues either. Lets see what happens.

<img width="860" alt="image" src="https://user-images.githubusercontent.com/108485221/224670597-f474e862-f89e-4302-b46b-85da3e05ffba.png">

It looks like the hypothesis was correct. Everything ran as expected and we got the desired outcome as well of a 1/1 score with no issues at all with this code.

This was also an exact result that we had desired to have happened when we ran the script against this GitHub repository.

## Code with Compile Error
This code most definetly should have a compile error. However it should crash right away though, since we are still expecting file headers to be correct, the code script should be able to find the file, but won't compile due to problems with the implementation. Lets see what happens

<img width="883" alt="Screen Shot 2023-03-13 at 3 10 47 AM" src="https://user-images.githubusercontent.com/108485221/224671571-edf3296f-9870-48b1-b434-07a48402cd83.png">

Seems like we would be correct in our assumption. The file was indeed found, but we also see that there was a message that popped up as we tried to compile the file, signalling that there is a compiling issue happening, in such the correct error was given of a compile error and a score of 0/1 as a result as well.

This too gave us the desired result and such is correct in the sense that it was able to detect the problema and not try to run tests as it won't compile.

## Code with Wrong File Name
With the wrong File name, there would be no way for the script to be able to find the file and run the tests on it. Since the scipt is only really meant to look for specific files, any file that is not the same will not be checked and tests be ran on it. In such we should be expecting the script to not be able to find the file and give a score of 0/1. Lets see.

<img width="868" alt="image" src="https://user-images.githubusercontent.com/108485221/224674184-2d0139f8-bbae-41c4-bd14-f87ccd2bd0e0.png">

Looks like the assumption is true, we could not evem find the file at all and in such there was no way the script would be able to run the test on the implementation at all. So the script is still working as expected and giving a score of 0/1 for not being able to find the file.

This once again also gave the expected output that we desired and everything looks to be checking out.

## Code Within a Folder
Sometimes things get uploaded with the folders. That doesn't mean anything is wrong, it just means we have to find it. In this instance, the file is correct and there is nothing wrong, it is just nested within a folder named PA1, so in theory, if we can get to the file, the tests should pass everything. Lets find out.

<img width="839" alt="Screen Shot 2023-03-13 at 3 53 02 AM" src="https://user-images.githubusercontent.com/108485221/224681311-60a27ac7-32fe-4f57-ace0-b283dd35c841.png">

Looks like everything is working as it should. The script was able to find a directory to direct it into the directory and find that yes the file does exists. And so the rest of the script can run and in doing so we can find that we can deduce the file is perfectly fine and is able to compile all that it needs.

This once again shows that proper functionality of the script and that it is functioning as we all expect it to.

## Conclusion
Overall, I felt that it was fun being able to work and mostly complete the script to test the files of good and bad implementation. I learned a lot of being able to use various types of command line arguments to make sure that I am able to run all the tests properly and correctly. However, this still doesn't stop the fact that this script still have long ways to go. Like with the instance of the method signiature, from my testing, that would easily pass everything that my script puts at it, but that is just as a result of lack of tests being applied. There is also the sense of the file within deeper directories. My implementation is only good enough to recognize the file by being able to get into the file, but it lacks getting back out to the directory in which we are trying to work in. There is definetly lots of things that I still need to learn in terms of working with command line arguments and using bash scripts, but I take this as a good launching spot for what I will learn in the future.
