# Week 1 (2023-01-12) - Remote Access

---


Whether you're my future self, another hypothetical 15L student who somehow found this page, or the person grading this page as an assignment, you may be looking at this page for a tutorial on how to log into an ieng6 account. There are three steps to this: installing VSCode, remotely connecting, and trying out commands, so let's get into it.

# Installing VSCode

To install VSCode, go to [this site](https://code.visualstudio.com/) and download the version of VSCode that you're looking for. Install VSCode through the download file and, once it's finished installing, any other extensions you may want for your purpose. Extensions and themes can be found in the sidebar under the magnifying glass icon. Personally, I didn't complete this step because I already had VSCode installed with all the necessary extensions that I wanted.

![Image](downloadingvscode.png)

# Remotely Connecting

Great! You know have VSCode. To remotely connect to a lab computer, open a new terminal window using the Terminal > New Terminal option in the top bar of the window. Type in `ssh cs15lwi23$$$@ieng6.ucsd.edu` into the terminal, with the $$$ being replaced with your course specific account numbers (mine is/was `agd`). If this is your first time, you may be given a `yes/no` prompt; just respond `yes`. Now, you should type in your password to the account; don't sweat it if it takes a few times, the system is finicky like that (read: my clumsy fingers didn't get it right the first 20 tries). The password won't be available because, well, it's a password. It'll be hidden, just like when websites fill in your passwords with a bunch of dots or \*\*\*\*\*\*\*\*\*\*\*\*.

Now that you've made it in, congrats! You should see something like the message printed below:

![Image](terminal.png)

# Trying Some Commands

Alright, let's test out some commands. Remember the meaning of different commands from lecture: cd means "change directory" and lets you enter or exit places along a path, `ls` means "list" and shows you stuff in the current location, and `mkdir` creates a directory (makes a folder).

![Image](commandsexample.png)

And that's it! Hope that was informative, or nostalgic to me-of-the-future.
