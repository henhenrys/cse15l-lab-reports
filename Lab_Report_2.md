# Servers and Bugs
## Part 1 - Servers
When we think of servers, we might think of it as some sort of place in which data is stored and accessed alike. And that is exactly what it is. Servers can be ran on essentially any type of computer, including your own machine. And in this example, we will be running a Simple String Server. We will make it so when we type something out into the URL, it will cause change into the actual server.

### The Code
<img width="551" alt="image" src="https://user-images.githubusercontent.com/108485221/215415842-38edf5f4-1bd5-4d2a-b2e7-43143bd38278.png">

In the above photo shows the code that is able to implment and allow for the Simple String Server to run. In it we see that we are able to identify what our URL looks like, and depending upon it will perform various tasks. In here it will take cases in which the path is either

```
/
```
or 

```
/add-message
```

or

```
/search
```
Once, the code has identified which path the URL is at, it will run the desired lines of code. In the case of the search and add-message, it will also look into the query for the type of argument it will perform.

### Executing Paths/Queries
<img width="1509" alt="image" src="https://user-images.githubusercontent.com/108485221/215416305-e87d1cb5-3e72-4c1b-955e-3e9a8730a834.png">
To begin with, here we are adding the word "Hello" in our String Server and will be saved within this web server. 

#### Arguments Made to Methods for #1
In order for this to be executed properly, the handleRequest method must be running, as it holds everything that is needed to properly add it in our server. Otherwise, we will need 

```
.getPath()
```

So we can see what path we are presently at. There isn't any argument needed for this besides having this only being able to work within URI type classes only.

```
.contains()
```

To see if the String has a sequence of charchers in the String. Seeing if something has anything similar to /add-message will allow us to know we are working in the correct path.

```
.getQuery()
```

To see what type of query arguement is being made. No real argument is being made, but it will give back the value of the query of the current URL.

```
.split()
```

In order to seperate a String Array based upon value being split. Some of the relevant arguments being made is "=" in which we will split the Array based upon the = in the query.

```
.equals()
```

A shallow comparrison between two objects to see if the two are equal. For instance, we here can check if the first index after the split is "s" to make sure we are in the correct querry.

```
.format()
```

Mainly used in a String, to format a String in a desired way. So if we don't know how how a value will be later on, we can make it so 

```
String.format(example %n, number)
```

```
example number
```

#### Changes to Relevant Values for #1

When working around with this, there were many variables that were defined and used when we were defining this. 

First we end up changing the String returning as an attempt contain of all of the items being added and so we would be able to have them all present in the main page. So the first "Hello" becomes a value in the returning variable and more and more will be added in an attempt to make showing all the words possible on the main page

Second, we ended up adding a value into ArrayList<String> returned, just so we can keep track of all that values being added in a sense where we can manipulate and use them later. Since ArrayList won't need the use of size, we just add the element value, "Hello", into the ArrayList and keep it there in an attempt for another use case.

Third, we end up having a different URI. Because we have something different than the base localhost:4000, the value of the URI is different and makes it so we are accessing a different part of the server.

Otherwise, no other variable were changed, as there is nothing else that is relevant in the purpose of the path/query and the other variables won't have any effect later on or presently.
  
<img width="1512" alt="image" src="https://user-images.githubusercontent.com/108485221/215416379-e6f0c047-3b26-421f-a200-e013e600a30d.png">

### Arguments Made to Methods for #2

A lot of the arguments made originally in the first screenshot, applies here too. Meaning, all the methods used in the first will be similarlly applied here too. All the methods being used and the arguments being passed to these methods are 
```
.getPath()
```

So we can see what path we are presently at. There isn't any argument needed for this besides having this only being able to work within URI type classes only.

```
.contains()
```

To see if the String has a sequence of charchers in the String. Seeing if something has anything similar to /add-message will allow us to know we are working in the correct path.

```
.getQuery()
```

To see what type of query arguement is being made. No real argument is being made, but it will give back the value of the query of the current URL.

```
.split()
```

In order to seperate a String Array based upon value being split. Some of the relevant arguments being made is "=" in which we will split the Array based upon the = in the query.

```
.equals()
```

A shallow comparrison between two objects to see if the two are equal. For instance, we here can check if the first index after the split is "s" to make sure we are in the correct querry.

```
.format()
```

Mainly used in a String, to format a String in a desired way. So if we don't know how how a value will be later on, we can make it so 

```
String.format(example %n, number)
```

```
example number
```

Essentially, all that was done originally for Screenshot 1 applies here as well.
  
#### Changes to Relevant Values for #2

Similarly, all the variables that were changed originally in the 1st screenshot will be changed here, and those that were changed won't either. However, the values will differ as we are dealing with another case. 

First, when we look at String returning, it will now contain both the previous word and the new word that has been added to the bank of words it now contains. It is also formatted in a sense where this new word will be in the next line, and not sequencial to the previous word of "Hello".
  
Secondly, in the ArrayList<String> returned will have a new value in the ArrayList. It will contain one more value, and will have one bigger size as a result of having one item being added into the ArrayList.
  
Third, the URI will be different as well. Since we are going to add "Bye" into the server, the query is also different as a result, to compensate for a different word being added.

Finally, like adding "Hello", no other variables will be changed and the values there will remain the exact same.

### The Main Page
<img width="1512" alt="image" src="https://user-images.githubusercontent.com/108485221/215416756-494b2141-a6e2-4b96-a3c3-696abbb72c55.png">
Here we are prompted with how the page looks like back in the main domain/home page of the web server. Here we are also able to see all the words that has been added into the server and is printed within the web server. In here nothing is really done besides returning the big returning variable that contains all that strings in a neat format.
  
### Finding All Strings With Given Substring
<img width="1512" alt="image" src="https://user-images.githubusercontent.com/108485221/215416814-7b3022ad-4f5e-4654-8b18-fbf4a3255db4.png">
This is different to the ones in which we were just adding things to our server. Here, we just want to look for words essentially that meet a certain criteria. Finding Strings that contains a sequencial similarity of what we input into the query.
### Arguments Made to Methods for #3
```
.getPath()
```

So we can see what path we are presently at. There isn't any argument needed for this besides having this only being able to work within URI type classes only.

```
.contains()
```

To see if the String has a sequence of charchers in the String. Seeing if something has anything similar to /add-message will allow us to know we are working in the correct path.

```
.getQuery()
```

To see what type of query arguement is being made. No real argument is being made, but it will give back the value of the query of the current URL.

```
.split()
```

In order to seperate a String Array based upon value being split. Some of the relevant arguments being made is "=" in which we will split the Array based upon the = in the query.

```
.equals()
```

A shallow comparrison between two objects to see if the two are equal. For instance, we here can check if the first index after the split is "s" to make sure we are in the correct querry.

```
.get()
```

Only used for Arraylist, but will give back a value based upon the index argument given into the method. Like .get(1), will give the value at index 1 of the ArrayList.
  
```
.size()
```
  
Only used for ArrayList, but will give the length of the ArrayList. Essentially gives back how many items are presently in the ArrayList. So if there were 2 items in the ArrayList, then .size() will get back 2.
  
#### Changes to Relevant Values for #3
There really isn't any value that are being changed here. Since this is mainly a comparison, only really one variable is changing its value constantly.

String returns is the only variable in which will need to have it's value changed as this essentially will return back all of the values that meet the criterias and formats and returns all values that is true.

### Concluding
Being able to implement this String Server required a lot of manipulation of variables and values. It made sure we had to make sure we called the right methods, and made sure to have make it so it will function properly.

## Part 2 - Bugs
Bugs are common when coding. It is almost expected that we wil not get our code necessarily correct and runs how we want it to be running. However, bugs are the end of the world, and we are able to diagnosis it and fix any issues

### ReverseInPlace Example
In this method, we expect that we get a reversed array when we input a Integer array. Like if we insert [2, 4, 6] turn into [6, 4, 2]. However this is not that case.


  
```
@Test 
public void testReverseInPlace() {
  int[] input2 = {1, 2, 3};
  ArrayExamples.reverseInPlace(input2);
  assertArrayEquals(new int[]{3, 2, 1}, input2);
}
```

The above code will cause a fail-inducing error, as the input is a valid input, but will cause a show the sypmtom of the bug.
  
  
```
@Test 
public void testReverseInPlace() {
  int[] input1 = { 3 };
  ArrayExamples.reverseInPlace(input1);
  assertArrayEquals(new int[]{ 3 }, input1);
}
```
  
However, this won't cause a fail-inducing error, and will actually pass the goal of the method as a whole.

<img width="692" alt="image" src="https://user-images.githubusercontent.com/108485221/215449263-1272d10d-3c44-42f8-a5ca-7088ef79fe83.png">
If we run the JUnit test, we can see that we are actually able to pass what was identified as the non-fail-inducing error, but will actually fail what we though would fail. Looking at the fail, it seems as though the method isn't properly reversing the array. As the array is changing values, the values changed isn't being temporarily held so it looks as though it is going [1, 2, 1] instead of [3, 2, 1].
  
  

Before:

```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
  
After:
  
```
    static void reverseInPlace(int[] arr) {
    int[] newArr = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArr[i] = arr[arr.length - 1 - i];
      System.out.println(newArr[i]);
    }
    for(int i = 0; i < arr.length; i++) {
      arr[i] = newArr[i];
    }
  }
```

Here, we are making a new array and copy values going from the reverse so we will do what the original method was attempting to do. And since we want the original array to become erased, we can set up a for loop and reassign the values of the old array to be the values of the new array.
### Reversed Example
In this method, we want to reverse the array that we inputed to the method, and assign a new array to be that reversed version of the original array and return that. However that is not what is going on in the method.

```
  @Test
  public void testReversed() {
  int[] input2 = {1, 2, 3};
  assertArrayEquals(new int[]{3, 2, 1}, ArrayExamples.reversed(input2));
  }
```

The code above will cause a fail-inducing error because, although it is a valid array input, it will return the wrong outputs.
      
```
  @Test
  public void testReversed() {
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
  }
```

The code above won't cause a fail-inducing error because it is a empty array, and reversing it will just give back an empty array.
                                  
<img width="813" alt="image" src="https://user-images.githubusercontent.com/108485221/215449447-42cabb5b-a451-4e2b-8bf5-1cd40c6fadae.png">
If we run our JUnit test, we can see that what we thought was going to pass, actually did pass. However, the fail case ended up being true and failed at the end. With knowing these symptoms, looking at the code, it looks as though the bug is caused flipping the newArray and arr in the for loop. We want to assign values to the newArray and not the old arr, as a result makes sense to why we got 0 as an output since, newArray is just a empty Integer array. All we would need to do is change the assignment to be newArray getting the contents of arr in reverse order and also returning the newArray instead of the old arr.
      
Before:
  
```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
      
After:
                                  
```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```

In the new version, we are doing exactly what I summarized earlier. We changed it so newArray is getting new values from the old arr. And instead of returning ther old arr, we will return the newArray instead.
## Part 3 - Conclusion
In the end, there were many things that I have been able to learn in these 2 labs. There were definitely many things that I never knew about, but now how some level of experience in it now. For instance, during the week 2 of lab, we were introduced to working with setting up a server. I had never actually had any experience running a server from a local machine or in general at all. Having gone through the lab, discussing what allow a server to function and understanding what methods and variables are needed to make it function properly. In the instance of the String Server, through the discussions I had, I realize we had to implment URLHandler to make sure to handle whatever is being thrown at it, and using our paths and queries to set up various different operations within the web server. At the end, there were still many more things that I have learned through all this, but I do feel that learning about servers was one of the most brain challenging thing thus far.
