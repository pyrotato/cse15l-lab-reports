# Week 5 (2023-01-12) - Remote Access

---


This week heralded the beginning of the end: the first Skill Demo in 15L. Even after practicing a bunch and making sure I got everything down on my notes, I'm still not confident in my performance. Because of that, here's some advice for the me of the future: get some sleep in before you do anything big.

In any case, for Week 5, we'll be going over researching command line interface (CLI) options, specifically for the `grep` command.

# grep -r \<string to be searched\>

```
// INPUT:
$ grep -r Honolulu

// OUPUT:
written_2/travel_guides/berlitz1/HandRHawaii.txt:        Oahu (Including Honolulu)
written_2/travel_guides/berlitz1/HandRHawaii.txt:        Aston Waikiki Sunset $$$ 229 Paoakalani Avenue, Honolulu, HI
written_2/travel_guides/berlitz1/HandRHawaii.txt:        Halekulani $$$$ 2199 Kalia Road, Honolulu, HI 96815; Tel.
written_2/travel_guides/berlitz1/HandRHawaii.txt:        Hilton Hawaiian Village $$$–$$$$ 2005 Kalia Road, Honolulu,
written_2/travel_guides/berlitz1/HandRHawaii.txt:        Honolulu, HI 96815; Tel. (808) 923-1234 or (800) 233-1234; fax (808)
written_2/travel_guides/berlitz1/HandRHawaii.txt:        half-hour drive of Honolulu. 387 rooms.
written_2/travel_guides/berlitz1/HandRHawaii.txt:        Honolulu, HI 96816; Tel. (808) 739-8888 or (800) 367-2525; fax (808)
written_2/travel_guides/berlitz1/HandRHawaii.txt:        Outrigger Reef $$$ 2169 Kalia Road, Honolulu, HI 96815; Tel.
written_2/travel_guides/berlitz1/HandRHawaii.txt:        Pacific Beach Hotel $$$ 2490 Kalakaua Avenue,, Honolulu, HI
written_2/travel_guides/berlitz1/HandRHawaii.txt:        Royal Hawaiian $$$$ 2259 Kalakaua Avenue, Honolulu, HI
written_2/travel_guides/berlitz1/HandRHawaii.txt:        Honolulu, HI 96815; Tel. (808) 922-3111 or (800) 325-3535; fax (808)
written_2/travel_guides/berlitz1/HandRHawaii.txt:        Honolulu, HI 96815; Tel. (808) 922-5811 or (800) 325-3535; fax (808)
written_2/travel_guides/berlitz1/HandRHawaii.txt:        Sheraton Waikiki $$$–$$$$ 2255 Kalakaua Avenue, Honolulu,
written_2/travel_guides/berlitz1/HistoryHawaii.txt:        church and the mission schools (which you can still visit in Honolulu)
written_2/travel_guides/berlitz1/HistoryHawaii.txt:        Honolulu. The Calvinistic reforms were soon reversed when Kaahumanu
written_2/travel_guides/berlitz1/HistoryHawaii.txt:        still be toured in Honolulu. He also legalized the hula, Hawaii’s
written_2/travel_guides/berlitz1/HistoryHawaii.txt:        governor was Dole. Queen Liliuokalani lived out her life near Honolulu,
written_2/travel_guides/berlitz1/WhatToHawaii.txt:        Midway. Lying some 1,100 miles northwest of Honolulu, Midway
```

```
// INPUT:
$ grep -r Mermaid

// OUPUT:
written_2/non-fiction/OUP/Castro/chM.txt:Mermaid 
```

# Remotely Connecting

Great! You now have VSCode. To remotely connect to a lab computer, open a new terminal window using the Terminal > New Terminal option in the top bar of the window. Type in `ssh cs15lwi23$$$@ieng6.ucsd.edu` into the terminal, with the $$$ being replaced with your course specific account numbers (mine is/was `agd`). If this is your first time, you may be given a `yes/no` prompt; just respond `yes`. Now, you should type in your password to the account; don't sweat it if it takes a few times, the system is finicky like that (read: my clumsy fingers didn't get it right the first 20 tries). 

> NOTE: The password may not be showing for you in Terminal, and that's okay, because it's a password. It'll be hidden, just like when websites hide your passwords with a bunch of dots or \*\*\*\*\*\*\*\*\*\*\*\*.

Now that you've made it in, congrats! You should see something like this printed to Terminal:

![Image](images/wk1/terminal.png)

# Trying Some Commands

Alright, let's test out some commands. Remember the meaning of different commands in Terminal: 

* `cd` means "change directory" and lets you enter or exit directories with a path 
* `ls` means "list" and shows you files and folders in the current location
* `mkdir` creates a directory (makes a folder).
* `cp` lets you copy files and directories
* `cat` is short for concatenate and lets you print a text file's contents, among other things

Additionally, when it comes to paths:

* `~` refers to your home directory
* `..` means to take a step back into the parent of your current directory

![Image](images/wk1/commandsexample.png)

# Closing Remarks

Remoting into a computer is a pretty common practice and is helpful to know about, especially during a time when remote work is becoming more and more popular (at the time of writing this). Chances are, you'll have to do it at some point in your career, so it's just a nice thing to know. Hopefully this tutorial was helpful, and if any particular situations or issues pop up, it may be helpful to look at documentation just to make sure you don't run `rm -rf /` on your system.

Maybe you might though, just for fun. Try it, who knows what will happen?
