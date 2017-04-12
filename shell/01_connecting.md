
# The Shell

## Why the Shell is important for Bioinformatics?

The *shell* is an environment that presents a command line interface (CLI)
which allows you to control a computer using commands entered
with a keyboard instead of controlling graphical user interfaces
(GUIs) with a mouse/keyboard combination.

There are many reasons to learn about the shell.

* For most bioinformatics tools, you have to use the shell. There is no
graphical interface. If you want to work in metagenomics or genomics you're
going to need to use the shell.
* The shell gives you *power*. The command line gives you the power to do your work more efficiently and
more quickly.  When you need to do things tens to hundreds of times,
knowing how to use the shell is transformative.
* To use remote computers or cloud computing, you need to use the shell.


![Automation](../img/gvng.jpg)

    Unix is user-friendly. It's just very selective about who its friends are.


Today we're going to go through how to access Unix/Linux and some of the basic
shell commands.


## Resources

Shell cheat sheets:

* [http://fosswire.com/post/2007/08/unixlinux-command-cheat-sheet/](http://fosswire.com/post/2007/08/unixlinux-command-cheat-sheet/)
* [https://github.com/swcarpentry/boot-camps/blob/master/shell/shell_cheatsheet.md](https://github.com/swcarpentry/boot-camps/blob/master/shell/shell_cheatsheet.md)

Explain shell - a web site where you can see what the different components of
a shell command are doing.  

* [http://explainshell.com](http://explainshell.com)
* [http://www.commandlinefu.com](http://www.commandlinefu.com)


## What is the shell?

At a high level, computers do four things:

-   run programs
-   store data
-   communicate with each other, and
-   interact with us

The shell is a longstanding interface for computers, and is, in fact, the simplest way for developers
to make their code available to users. This kind of interface is called a
**command-line interface**, or CLI, to distinguish it from a
**graphical user interface**, or GUI, which most people now use.
The heart of a CLI is a **read-evaluate-print loop**, or REPL:
when the user types a command and then presses the Enter (or Return) key,
the computer reads it, executes it, and prints its output.
The user then types another command, and so on until the user logs off.

This description makes it sound as though the user sends commands directly to the computer,
and the computer sends output directly to the user.
In fact, there is usually a program in between called a
**command shell**. What the user types goes into the shell,
which then figures out what commands to run and orders the computer to execute them.
(Note that the shell is called "the shell" because it encloses the operating system "kernel"
in order to hide some of its complexity and make it simpler to interact with.)

A shell is a program like any other.
What's special about it is that its job is to run other programs
rather than to do calculations itself.
The most popular Unix shell is Bash,
the Bourne Again SHell
(so-called because it's derived from a shell written by Stephen Bourne).
Bash is the default shell on most modern implementations of Unix
and in most packages that provide Unix-like tools for Windows.

Using Bash or any other shell
sometimes feels more like programming than like using a mouse.
Commands are terse (often only a couple of characters long),
their names are frequently cryptic,
and their output is lines of text rather than something visual like a graph.
On the other hand,
with only a few keystrokes, the shell allows us to combine existing tools into 
powerful pipelines and handle large volumes of data automatically. This automation
not only makes us more productive but also improves the reproducibility of our workflows by 
allowing us to repeat them with few simple commands.
In addition, the command line is often the easiest way to interact with remote machines and supercomputers.
Familiarity with the shell is near essential to run a variety of specialized tools and resources
including high-performance computing systems.
As clusters and cloud computing systems become more popular for scientific data crunching,
being able to interact with the shell is becoming a necessary skill.
We can build on the command-line skills covered here
to tackle a wide range of scientific questions and computational challenges.


## Accessing the Shell

Mac
---  
On Mac the shell is available through Terminal  
Applications -> Utilities -> Terminal  
Go ahead and drag the Terminal application to your Dock for easy access.

Windows
-------
For Windows, you need a third party application (called a SSH client) to connect to a shell. We recommend MobaXterm
for this class: [http://mobaxterm.mobatek.net/download.html](http://mobaxterm.mobatek.net/download.html).  
There are other options, of course.  It is worth noting that Windows 10 has an optional "Bash Shell Environment"
that can be installed.

Linux  
-----
The shell is available by default on Linux through the "Terminal" application.  You should be set.


## Connecting to another computer through SSH

To provide a more consistent environment for this class, we will connect to the University of Hawaii HPC center.

If you do not have a username and password for the UH HPC system, let one of the instructors know now, and we can help you.
More information on connecting to the HPC system is here: http://www.hawaii.edu/its/ci/hpc-resources/hpc-quick-start-guide/

Once you know your username and password, you are ready to open up your terminal or ssh client and connect:

```ssh USERNAME@uhhpc1.its.hawaii.edu```

    Note: When you are asked for a password, the characters you type will not be
    displayed.  The cursor just stays in the same spot even though it is 
    receiving everything you type.

Once you have connected to the HPC center, you are ready to start managing data in the next section.

[Back](index.md) | [Next: Navigating the Filesystem](02_the_filesystem.md)