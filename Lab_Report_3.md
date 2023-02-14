# Researching Commands
Through the 3 weeks of Lab Reports, we have gotten better at working with command line arguments. We have have experience using commands like ls, cd, rm, find, grep, and many other as well. However, we have only really looked at the surface of some of these commands. Many of these commands have other capabilities that can perform tasks faster and more effiecient as well.
## Alternate Command Line Options/Alternate Ways of use of find
For this example, I will be looking at the alternate command line options for the find commmand. Thus far, we have only really used the alternate way of -name in which we were able to find certain files that contains a certain pattern given in the command line argument.
### Interesting Command Line Argument #1 | -empty
The -empty command is used in tandem with the find command. The whole goal of the -empty is to look through the given directory and its sub-directories to see if there is any files/directories that are empty, void of any data.

For example if we look at the skill-demo1-data file that was a part of the skills demo 1, we can perform the given -empty command. For the sake of example, if we perform 

```
$ mkdir example
```

in the written_2 folder, we should have a empty directory and thus, the -empty should be able to find it as it is the only thing that is empty in all of the written_2 folder. So, if we perform 

```
$ find written_2 -empty
```

we should get the resulting path of

```
written_2/example
```
That's great, we found the empty directory in the written_2 folder. That was the goal and we were able to do that. That being said, that isn't the only way to use the -empty command. The capability of -empty also goes to individual files as well. For instance, if we perform
```
$ touch example2.txt
```
into the written 2 directory also, we know that this is a txt file and not a specific directory like that of example. However, since the example2.txt file is empty, the -empty file should be able to find it. So once we perform 
```
$ find written_2 -empty
```
it gives that given output of
```
written_2/example
written_2/example2.txt
```
As we expected, it give out all the empty files and empty directories as well. This is exactly the result that we wanted, as the code looked through everythng that was empty and gave back the desired directories.

Essentially in doing -empty, it is looking through all the possible paths within the written_2 directory and finds at what points will lead to an empty file or directory and prints those paths out into the terminal. This is generally a useful command just to clean up your machine, it removes all the unnecessary clutter within your machine, or easily find the files that were empty and edit edit them also. In general, it is a simple command that will allow us to perform general cleansing of the machine of clutter. I was able to come accross the command through the 
```
man find
```
command and found the -empty and its description of its performance.

And originally I came accross this command line argument from [https://geekflare.com/linux-find-commands/](https://geekflare.com/linux-find-commands/)
### Interesting Command Line Argument #2 | -delete
The -delete command is very useful in getting rid of files, directories, and anything that has been found. As I talked about earlier, the -empty command is good to find out anything empty given the path. Thus, using it with -delete could allow for the file to be cleansed easily.

For example, we could apply this logic into the two empty things that we had identified earlier using
```
$ find written_2 -empty -delete
```
Once we do this, there should be nothing empty within the written_2 directory. Doing 
``` 
$ find written_2 -empty
```
will just give us
```
$
```
As we see, there is no output given, and instead left us to put other command line arguments instead. With this in mind, there is no empty files present now as typically it would print out the paths of the empty files/directories.

Same thing could be done if we just want to just remove a singlular thing. So lets pretend to add two different thing, a directory
```
$ mkdir examples
```
and a file 
``` 
touch examples.txt
```
Once we do
```
$ ls
```
we should get 
```
non-fiction  travel_guides  examples  examples.txt
```
Lets say we just want to remove the examples.txt file because it is useless and has no importance to the written_2 directory. Then we could do
```
$ find "examples.txt" -delete
``` 
we would remove examples.txt and when we do 
```
$ ls
```
we would have
```
non-fiction  travel_guides  examples
```
Which is exactly what we wanted.

When we do the -delete command, we essentially are removing whatever arguments that we have given the -remove. So when were looking at all the empty files/directories, the -remove argument allowed to so it instantly removes all the files given as argument. As a overall, the functionality of -delete is just to remove whatever is passed in as argument in the command line. This is useful because it allows us to generalize whatever we want to remove. It simplifies tedious actions and makes it so it can be as fast or faster than manually deleting the given thing. Once again, I was able to come accross this command through using 
```
man find
```
and reading through the description that was given for the command. And following the performance of -delete through my own practice.

I also originally discovered this command through [https://geekflare.com/linux-find-commands/](https://geekflare.com/linux-find-commands/).
### Interesting Command Line Argument #3 | -size n
Being able to see what type of files takes up the most space can be useful. We will be able to see what are things that exceed a certain amount of bytes, and can delete them or change them acordingly. Say for instance we want to find out what is the smallest things are in the written_2 folder, we could do
```
$ find written_2 -size -2K
```
and we would get 
```
written_2/travel_guides/berlitz1/HandRIbiza.txt
written_2/travel_guides/berlitz1/HandRIstanbul.txt
written_2/example.txt
```
as these are the only files that are less than 2 killobytes. Essentially what the code has done is look through all the files within the written_2 directory and print out paths that are smaller than 2 killobytes in size.

Lets also say we want to look for some big files within the written_2 folder, same can be done as well. We can do
``` 
$ find written_2 -size +200k
```
and we would get
``` 
written_2/travel_guides/berlitz1/WhereToFrance.txt
written_2/travel_guides/berlitz1/WhereToItaly.txt
written_2/travel_guides/berlitz2/Canada-WhereToGo.txt
```
as these are files that are greater than 200 killobytes in size. As a general the code was used to look through all the files in written_2 and print out paths to files that are greater than 200 killobytes in size.

As a whole, the -size n allows us to look for files within our directory and look for whether it is bigger, smaller, or exactly given the command line argument. The various +, -, or *blank* will offer different meanings, as + means greater than the given number, - means less than, and nothing is just exact. Also the letters play into effect as well to determine the type of data size, from killobyte to megabyte. This is useful in helping identifying files that are taking up large sums of storage and identifying whether or not that given file is useful to us or not. Again, the command was found using the
```
man find
```
command where I was able to read up on the -size n command and that functionality of it.

Originally, I did find this command line argument also at [https://geekflare.com/linux-find-commands/](https://geekflare.com/linux-find-commands/).
### Interesting Command Line Argument #4 | -type n
It is nice sometimes to just look for things specific to files/directories, or anything else. Being able to differentiate and isolate things specifically will just make out lives easier. Doing so will make it so we wouldn't need to use `ls` every time we want to find any file. It can also be used to find all of our .txt files faster too. For instance, lets say we want to see how many directories there are in the written_2 folder, because we want to isolate each directory for it's own purpose, we would do
```
$ find written_2 -type d
```
where it would result in
```
written_2
written_2/non-fiction
written_2/non-fiction/OUP
written_2/non-fiction/OUP/Abernathy
written_2/non-fiction/OUP/Berk
written_2/non-fiction/OUP/Castro
written_2/non-fiction/OUP/Fletcher
written_2/non-fiction/OUP/Kauffman
written_2/non-fiction/OUP/Rybczynski
written_2/travel_guides
written_2/travel_guides/berlitz1
written_2/travel_guides/berlitz2
```
giving us all the directories that we have access to within the written_2 directory.

Lets also say we want to see all the files in general, then we could do
```
$ find written_2 -type f
```
which would give us 
```
written_2/non-fiction/OUP/Abernathy/ch1.txt
written_2/non-fiction/OUP/Abernathy/ch14.txt
written_2/non-fiction/OUP/Abernathy/ch15.txt
written_2/non-fiction/OUP/Abernathy/ch2.txt
written_2/non-fiction/OUP/Abernathy/ch3.txt
written_2/non-fiction/OUP/Abernathy/ch6.txt
written_2/non-fiction/OUP/Abernathy/ch7.txt
written_2/non-fiction/OUP/Abernathy/ch8.txt
written_2/non-fiction/OUP/Abernathy/ch9.txt
written_2/non-fiction/OUP/Berk/CH4.txt
written_2/non-fiction/OUP/Berk/ch1.txt
written_2/non-fiction/OUP/Berk/ch2.txt
written_2/non-fiction/OUP/Berk/ch7.txt
written_2/non-fiction/OUP/Castro/chA.txt
written_2/non-fiction/OUP/Castro/chB.txt
written_2/non-fiction/OUP/Castro/chC.txt
written_2/non-fiction/OUP/Castro/chL.txt
written_2/non-fiction/OUP/Castro/chM.txt
written_2/non-fiction/OUP/Castro/chN.txt
written_2/non-fiction/OUP/Castro/chO.txt
written_2/non-fiction/OUP/Castro/chP.txt
written_2/non-fiction/OUP/Castro/chQ.txt
written_2/non-fiction/OUP/Castro/chR.txt
written_2/non-fiction/OUP/Castro/chV.txt
written_2/non-fiction/OUP/Castro/chW.txt
written_2/non-fiction/OUP/Castro/chY.txt
written_2/non-fiction/OUP/Castro/chZ.txt
written_2/non-fiction/OUP/Fletcher/ch1.txt
written_2/non-fiction/OUP/Fletcher/ch10.txt
written_2/non-fiction/OUP/Fletcher/ch2.txt
written_2/non-fiction/OUP/Fletcher/ch5.txt
written_2/non-fiction/OUP/Fletcher/ch6.txt
written_2/non-fiction/OUP/Fletcher/ch9.txt
written_2/non-fiction/OUP/Kauffman/ch1.txt
written_2/non-fiction/OUP/Kauffman/ch10.txt
written_2/non-fiction/OUP/Kauffman/ch3.txt
written_2/non-fiction/OUP/Kauffman/ch4.txt
written_2/non-fiction/OUP/Kauffman/ch5.txt
written_2/non-fiction/OUP/Kauffman/ch6.txt
written_2/non-fiction/OUP/Kauffman/ch7.txt
written_2/non-fiction/OUP/Kauffman/ch8.txt
written_2/non-fiction/OUP/Kauffman/ch9.txt
written_2/non-fiction/OUP/Rybczynski/ch1.txt
written_2/non-fiction/OUP/Rybczynski/ch2.txt
written_2/non-fiction/OUP/Rybczynski/ch3.txt
written_2/travel_guides/berlitz1/HandRHawaii.txt
written_2/travel_guides/berlitz1/HandRHongKong.txt
written_2/travel_guides/berlitz1/HandRIbiza.txt
written_2/travel_guides/berlitz1/HandRIsrael.txt
written_2/travel_guides/berlitz1/HandRIstanbul.txt
written_2/travel_guides/berlitz1/HandRJamaica.txt
written_2/travel_guides/berlitz1/HandRJerusalem.txt
written_2/travel_guides/berlitz1/HandRLakeDistrict.txt
written_2/travel_guides/berlitz1/HandRLasVegas.txt
written_2/travel_guides/berlitz1/HandRLisbon.txt
written_2/travel_guides/berlitz1/HandRLosAngeles.txt
written_2/travel_guides/berlitz1/HandRMadeira.txt
written_2/travel_guides/berlitz1/HandRMadrid.txt
written_2/travel_guides/berlitz1/HandRMallorca.txt
written_2/travel_guides/berlitz1/HistoryDublin.txt
written_2/travel_guides/berlitz1/HistoryEdinburgh.txt
written_2/travel_guides/berlitz1/HistoryEgypt.txt
written_2/travel_guides/berlitz1/HistoryFWI.txt
written_2/travel_guides/berlitz1/HistoryFrance.txt
written_2/travel_guides/berlitz1/HistoryGreek.txt
written_2/travel_guides/berlitz1/HistoryHawaii.txt
written_2/travel_guides/berlitz1/HistoryHongKong.txt
written_2/travel_guides/berlitz1/HistoryIbiza.txt
written_2/travel_guides/berlitz1/HistoryIndia.txt
written_2/travel_guides/berlitz1/HistoryIsrael.txt
written_2/travel_guides/berlitz1/HistoryIstanbul.txt
written_2/travel_guides/berlitz1/HistoryItaly.txt
written_2/travel_guides/berlitz1/HistoryJamaica.txt
written_2/travel_guides/berlitz1/HistoryJapan.txt
written_2/travel_guides/berlitz1/HistoryJerusalem.txt
written_2/travel_guides/berlitz1/HistoryLakeDistrict.txt
written_2/travel_guides/berlitz1/HistoryLasVegas.txt
written_2/travel_guides/berlitz1/HistoryMadeira.txt
written_2/travel_guides/berlitz1/HistoryMadrid.txt
written_2/travel_guides/berlitz1/HistoryMalaysia.txt
written_2/travel_guides/berlitz1/HistoryMallorca.txt
written_2/travel_guides/berlitz1/IntroDublin.txt
written_2/travel_guides/berlitz1/IntroEdinburgh.txt
written_2/travel_guides/berlitz1/IntroEgypt.txt
written_2/travel_guides/berlitz1/IntroFWI.txt
written_2/travel_guides/berlitz1/IntroFrance.txt
written_2/travel_guides/berlitz1/IntroGreek.txt
written_2/travel_guides/berlitz1/IntroHongKong.txt
written_2/travel_guides/berlitz1/IntroIbiza.txt
written_2/travel_guides/berlitz1/IntroIndia.txt
written_2/travel_guides/berlitz1/IntroIsrael.txt
written_2/travel_guides/berlitz1/IntroIstanbul.txt
written_2/travel_guides/berlitz1/IntroItaly.txt
written_2/travel_guides/berlitz1/IntroJamaica.txt
written_2/travel_guides/berlitz1/IntroJapan.txt
written_2/travel_guides/berlitz1/IntroJerusalem.txt
written_2/travel_guides/berlitz1/IntroLakeDistrict.txt
written_2/travel_guides/berlitz1/IntroLasVegas.txt
written_2/travel_guides/berlitz1/IntroLosAngeles.txt
written_2/travel_guides/berlitz1/IntroMadeira.txt
written_2/travel_guides/berlitz1/IntroMadrid.txt
written_2/travel_guides/berlitz1/IntroMalaysia.txt
written_2/travel_guides/berlitz1/IntroMallorca.txt
written_2/travel_guides/berlitz1/JungleMalaysia.txt
written_2/travel_guides/berlitz1/WhatToDublin.txt
written_2/travel_guides/berlitz1/WhatToEdinburgh.txt
written_2/travel_guides/berlitz1/WhatToEgypt.txt
written_2/travel_guides/berlitz1/WhatToFWI.txt
written_2/travel_guides/berlitz1/WhatToFrance.txt
written_2/travel_guides/berlitz1/WhatToGreek.txt
written_2/travel_guides/berlitz1/WhatToHawaii.txt
written_2/travel_guides/berlitz1/WhatToHongKong.txt
written_2/travel_guides/berlitz1/WhatToIbiza.txt
written_2/travel_guides/berlitz1/WhatToIndia.txt
written_2/travel_guides/berlitz1/WhatToIsrael.txt
written_2/travel_guides/berlitz1/WhatToIstanbul.txt
written_2/travel_guides/berlitz1/WhatToItaly.txt
written_2/travel_guides/berlitz1/WhatToJamaica.txt
written_2/travel_guides/berlitz1/WhatToJapan.txt
written_2/travel_guides/berlitz1/WhatToLakeDistrict.txt
written_2/travel_guides/berlitz1/WhatToLasVegas.txt
written_2/travel_guides/berlitz1/WhatToLosAngeles.txt
written_2/travel_guides/berlitz1/WhatToMadeira.txt
written_2/travel_guides/berlitz1/WhatToMalaysia.txt
written_2/travel_guides/berlitz1/WhatToMallorca.txt
written_2/travel_guides/berlitz1/WhereToDublin.txt
written_2/travel_guides/berlitz1/WhereToEdinburgh.txt
written_2/travel_guides/berlitz1/WhereToEgypt.txt
written_2/travel_guides/berlitz1/WhereToFWI.txt
written_2/travel_guides/berlitz1/WhereToFrance.txt
written_2/travel_guides/berlitz1/WhereToGreek.txt
written_2/travel_guides/berlitz1/WhereToHawaii.txt
written_2/travel_guides/berlitz1/WhereToHongKong.txt
written_2/travel_guides/berlitz1/WhereToIbiza.txt
written_2/travel_guides/berlitz1/WhereToIndia.txt
written_2/travel_guides/berlitz1/WhereToIsrael.txt
written_2/travel_guides/berlitz1/WhereToIstanbul.txt
written_2/travel_guides/berlitz1/WhereToItaly.txt
written_2/travel_guides/berlitz1/WhereToJapan.txt
written_2/travel_guides/berlitz1/WhereToJerusalem.txt
written_2/travel_guides/berlitz1/WhereToLakeDistrict.txt
written_2/travel_guides/berlitz1/WhereToLosAngeles.txt
written_2/travel_guides/berlitz1/WhereToMadeira.txt
written_2/travel_guides/berlitz1/WhereToMadrid.txt
written_2/travel_guides/berlitz1/WhereToMalaysia.txt
written_2/travel_guides/berlitz1/WhereToMallorca.txt
written_2/travel_guides/berlitz2/Algarve-History.txt
written_2/travel_guides/berlitz2/Algarve-Intro.txt
written_2/travel_guides/berlitz2/Algarve-WhatToDo.txt
written_2/travel_guides/berlitz2/Algarve-WhereToGo.txt
written_2/travel_guides/berlitz2/Amsterdam-History.txt
written_2/travel_guides/berlitz2/Amsterdam-Intro.txt
written_2/travel_guides/berlitz2/Amsterdam-WhatToDo.txt
written_2/travel_guides/berlitz2/Amsterdam-WhereToGo.txt
written_2/travel_guides/berlitz2/Athens-History.txt
written_2/travel_guides/berlitz2/Athens-Intro.txt
written_2/travel_guides/berlitz2/Athens-WhatToDo.txt
written_2/travel_guides/berlitz2/Athens-WhereToGo.txt
written_2/travel_guides/berlitz2/Bahamas-History.txt
written_2/travel_guides/berlitz2/Bahamas-Intro.txt
written_2/travel_guides/berlitz2/Bahamas-WhatToDo.txt
written_2/travel_guides/berlitz2/Bahamas-WhereToGo.txt
written_2/travel_guides/berlitz2/Bali-History.txt
written_2/travel_guides/berlitz2/Bali-WhatToDo.txt
written_2/travel_guides/berlitz2/Bali-WhereToGo.txt
written_2/travel_guides/berlitz2/Barcelona-History.txt
written_2/travel_guides/berlitz2/Barcelona-WhatToDo.txt
written_2/travel_guides/berlitz2/Barcelona-WhereToGo.txt
written_2/travel_guides/berlitz2/Beijing-History.txt
written_2/travel_guides/berlitz2/Beijing-WhatToDo.txt
written_2/travel_guides/berlitz2/Beijing-WhereToGo.txt
written_2/travel_guides/berlitz2/Berlin-History.txt
written_2/travel_guides/berlitz2/Berlin-WhatToDo.txt
written_2/travel_guides/berlitz2/Berlin-WhereToGo.txt
written_2/travel_guides/berlitz2/Bermuda-WhatToDo.txt
written_2/travel_guides/berlitz2/Bermuda-WhereToGo.txt
written_2/travel_guides/berlitz2/Bermuda-history.txt
written_2/travel_guides/berlitz2/Boston-WhereToGo.txt
written_2/travel_guides/berlitz2/Budapest-History.txt
written_2/travel_guides/berlitz2/Budapest-WhatToDo.txt
written_2/travel_guides/berlitz2/Budapest-WhereoGo.txt
written_2/travel_guides/berlitz2/California-History.txt
written_2/travel_guides/berlitz2/California-WhatToDo.txt
written_2/travel_guides/berlitz2/California-WhereToGo.txt
written_2/travel_guides/berlitz2/Canada-History.txt
written_2/travel_guides/berlitz2/Canada-WhereToGo.txt
written_2/travel_guides/berlitz2/CanaryIslands-History.txt
written_2/travel_guides/berlitz2/CanaryIslands-WhatToDo.txt
written_2/travel_guides/berlitz2/CanaryIslands-WhereToGo.txt
written_2/travel_guides/berlitz2/Cancun-History.txt
written_2/travel_guides/berlitz2/Cancun-WhatToDo.txt
written_2/travel_guides/berlitz2/Cancun-WhereToGo.txt
written_2/travel_guides/berlitz2/China-History.txt
written_2/travel_guides/berlitz2/China-WhatToDo.txt
written_2/travel_guides/berlitz2/China-WhereToGo.txt
written_2/travel_guides/berlitz2/Costa-History.txt
written_2/travel_guides/berlitz2/Costa-WhatToDo.txt
written_2/travel_guides/berlitz2/Costa-WhereToGo.txt
written_2/travel_guides/berlitz2/CostaBlanca-History.txt
written_2/travel_guides/berlitz2/CostaBlanca-WhatToDo.txt
written_2/travel_guides/berlitz2/Crete-History.txt
written_2/travel_guides/berlitz2/Crete-WhatToDo.txt
written_2/travel_guides/berlitz2/Crete-WhereToGo.txt
written_2/travel_guides/berlitz2/CstaBlanca-WhereToGo.txt
written_2/travel_guides/berlitz2/Cuba-History.txt
written_2/travel_guides/berlitz2/Cuba-WhatToDo.txt
written_2/travel_guides/berlitz2/Cuba-WhereToGo.txt
written_2/travel_guides/berlitz2/Nepal-History.txt
written_2/travel_guides/berlitz2/Nepal-WhatToDo.txt
written_2/travel_guides/berlitz2/Nepal-WhereToGo.txt
written_2/travel_guides/berlitz2/NewOrleans-History.txt
written_2/travel_guides/berlitz2/Paris-WhatToDo.txt
written_2/travel_guides/berlitz2/Paris-WhereToGo.txt
written_2/travel_guides/berlitz2/Poland-History.txt
written_2/travel_guides/berlitz2/Poland-WhatToDo.txt
written_2/travel_guides/berlitz2/Portugal-History.txt
written_2/travel_guides/berlitz2/Portugal-WhatToDo.txt
written_2/travel_guides/berlitz2/Portugal-WhereToGo.txt
written_2/travel_guides/berlitz2/PuertoRico-History.txt
written_2/travel_guides/berlitz2/PuertoRico-WhatToDo.txt
written_2/travel_guides/berlitz2/PuertoRico-WhereToGo.txt
written_2/travel_guides/berlitz2/Vallarta-History.txt
written_2/travel_guides/berlitz2/Vallarta-WhatToDo.txt
written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt
```
which is all the files inside of the written_2 directory. This is also very much easier than that of the way we were taught in class too, needing fewer characters to achieve the same goal. 

As a whole, the -type n allows us to isolate certain types of things, based on their categorization. There are many key values that mean different things, like how f is a general file, and d is directories. This just simplifies the way to look for certain things based upon their categorization. This is useful as it becomes a tool to find things in relation to their typing. It makes it so if we are only dealing with directories, we can easily pull up every directory in the given folder for our use case. Lastly, I also found this again by using the
``` 
man find
```
command in the terminal and used the description that was given to make examples and explain its functionality.

I originally discovered this at [https://geekflare.com/linux-find-commands/](https://geekflare.com/linux-find-commands/) as well, and found out more on it as I looked on `man find`.
## Couclusion
As a whole, every command that we can do in the terminal isn't a one sided command, only able to execute things based on what their initial build is. It does open my eyes up to seeing what more can these commands do. As we know that there are many commands out there, they all have some sort of function, and contribute in same way to being useful. It does make me feel way more confident that I still have more to learn about commands and that I still have more to grow. I feel with every day that goes by, I and my peers will learn more and more and become more capable in these commands.
