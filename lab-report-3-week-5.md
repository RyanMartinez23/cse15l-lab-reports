# **WEEK 5 LAB REPORT 3**
**Introduction:** This week I decided to research some commands for grep. According to my sources Grep is a Unix utility that searches through either information piped to it or files in the current directory(wikibooks.org). For example you can use grep to search for a specific word in a file. 
<br> 
> **grep [options] pattern [files]** 

<br>
Above is the basic sytax for using grep their are many command line options with grep. For this lab I will be explaining three options each with 3 example on how to use these grep options.

<br>
The first grep option is -i it ignores case for matching. 

>**$ grep -i "text" demo_file**

This option enables top search for a string case insentively in a file. The follwing demo_file will be used to show examples:

    unix is great os. unix is free os.
    learn operating system.
    Unix linux which one you choose.
    uNix is easy to learn.unix is a multiuser os.
    Learn unix .unix is a powerful.

**An example** of this is when searching for a word

>**grep -i "unix" demo_file**

The output:
    
    unix is great os. unix is free os.
    Unix linux which one you choose.
    uNix is easy to learn.unix is a multiuser os.
    Learn unix .unix is a powerful.
because all the lines contain unix and case sensitivity is ignored due to -i

**Another Example** would be 

>**grep -i "learn" demo_file**

The output:
    
    learn operating system.
    uNix is easy to learn.unix is a multiuser os.
    Learn unix .unix is a powerful.
because all the lines contain learn and case sensitivity is ignored due to -i

**My Third example** of using -i is when trying to find a command error where you could have named the input incorrectly such as FILE instead of File and now you need to find your error. using grep -i will allow you to find all strings with the same characters regardless of case sensitivity. 


**The Second grep option is -A, -B, and -C**
<br>
When doing a grep on a huge file grep can show you not only the matching lines but also the lines after/before/around the match.
The syntax for this option is:
>**grep -B <N\> "string" FILENAME**

We will be using the follwing demo_text for examples.

    You may want to do several navigation in relation to the words, such as:
    * e - go to the end of the current word.
    * E - go to the end of the current WORD.
    * b - go to the previous (before) word.
    * B - go to the previous (before) WORD.
    * w - go to the next word.
    * W - go to the next WORD.

    WORD - WORD consists of a sequence of non-blank characters, separated with white space.
    word - word consists of a sequence of letters, digits and underscores.

    Example to show the difference between WORD and word

    * 192.168.1.1 - single WORD
    *192.168.1.1 - seven words. 

<br>

**The first example uses -A** and -i but looking closely you see that after -A their is a number this number tells grep the number of lines to print after the word.

>$ grep -A 3 -i "example" demo_text

The Output: 

    Example to show the difference between WORD and word

    * 192.168.1.1 - single WORD
    * 192.168.1.1 - seven words.
-A is used for printing lines after the match.

**The second example is using -B**
>$ grep -B 2 "single WORD" demo_text

The Output: 
   
    Example to show the difference between WORD and word
    * 192.168.1.1 - single WORD
    
-B is used to print the lines before the match.

**The third example is using -C**
>$ grep -C 2 "Example" demo_text

The Output: 
   
    word - word consists of a sequence of letters, digits and underscores.

    Example to show the difference between WORD and word

    * 192.168.1.1 - single WORD
    
-C is used to print the lines before and after the match.

**The Third grep option is -o**

By default grep will show the line with the match, but if you want only the match then use the -o option. The syntax for this option looks like this:

>**$ grep -o "text" demo_file**

**My first example** of using this is to print a word that is used multiple times. For example using the same demo_text from above and using:

>*$ grep -o "go" demo_text** 

The Output will be: 

    go
    go
    go
    go
    go
    go

This paired along with other options can be vary useful. 

**An Example** of -o being useful is when it's paried up with -b:

file.txt is our example txt file:

    12345
    12345

>grep -o -b "3" file
The Output:
    
    $ grep -o -b "3" temp-file.txt
    2:3
    8:3
This combination gives of the position of the string we were looking for.

**My final example** using -o is pairing -o with a regex pattern. A regular expression patter is sequence of characters that specifies a search pattern in text.
For Example:

>**$ grep -o "is.*line" demo_file**

Output:

    is line is the 1st lower case line
    is line
    is is the last line

This helps find words in specific spots. 

**Conclusion:** I went over some grep options that I found interesting, but there are too many grep options to discuss and the great thing about these options is that they can be paired together. I listed my work cited below check out the links as they have more information on different types of grep options including using pipe with grep.  







                                                        Work Cited

    “GREP Command in Unix/Linux.” GeeksforGeeks, 1 Nov. 2022, https://www.geeksforgeeks.org/grep-command-in-unixlinux/. 
    projects, Contributors to Wikimedia. “GREP.” Wikibooks, Open Books for an Open World, Wikimedia Foundation, Inc., 4 Sept. 2022, https://en.wikibooks.org/wiki/Grep. 
    SathiyaMoorthy. “15 Practical GREP Command Examples in Linux / Unix.” The Geek Stuff, 12 June 2014, https://www.thegeekstuff.com/2009/03/15-practical-unix-grep-command-examples/. 





