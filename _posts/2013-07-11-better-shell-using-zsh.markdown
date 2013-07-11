---
layout: post
title:  "Better shell using Zsh"
date:   2013-07-11 21:00:04
categories: article
comments: true
---
#####1. What in the world is Zsh?
ZSH or Z shell is a unix shell that can be used as an interactive login shell and as a powerfull command interpreter of shell scripting. Zsh can be bought of as extend Bourne shell (Bash) with a large of improvement, including some features of Bash, ksh, and tcsh

**Donald Knuth**

![Alt text](http://www.collegecrunch.org/wp-content/uploads/2010/03/donald_knuth.jpg "Donald Knuth")

Professor Emeritus of the Art of Computer Programming at Stanford University. In 1986 Knuth was asked to write a guest feature for the "Programing Pearls" column in the Comunication of the ACM Journal.

The task is to write a program that would: read a file of text, determine the n most frequently used words, and print out sorted list of those words along with their frequencies.

Knuth produced a solution in Pascal that, when printed, was about 10 pages in length. It was well designed, thoroughly commented, and used a novel data structure for managing the word count list

In response, Doug Mcllroy wrote a shell script that produced the same output.

Mcllroy's script was six lines long.
{% highlight sh linenos %}
tr -cs A-Za-Z '\n' |
tr A-Z a-z |
sort |
uniq -c |
sort -rn |
sed ${1}q
{% endhighlight %}
#####2. A brief History of shells
**Thompson shell**(1971) the first unix shell, writen by _Ken Thompson_ at Bell Labs. Distributed with version 1 through 6 of unix, from 1971 to 1975. Considered very rudimentary by modern standards and not used on current systems, though available as part of some Ancient UNIX Systems.

**Bourne shell**(1977) was one of the major shells used in early versions of the Unix operating system and became a de facto standard. It was written by Stephen Bourne at Bell Labs and was first distributed with Version 7 Unix, circa 1977. Every Unix-like system has at least one shell compatible with the Bourne shell. The Bourne shell program name is sh and it is typically located in the Unix file system hierarchy at `/bin/sh`. On many systems, however, `/bin/sh` may be a symbolic link or hard link to a compatible, but more feature-rich shell than the Bourne shell. The POSIX standard specifies its standard shell as a strict subset of the Korn shell. From a user's perspective the Bourne shell was immediately recognized when active by its characteristic default 

**C shell**(1978) was developed by Bill Joy for the Berkeley Software Distribution, a line of Unix operating systems derived from Unix and developed at the University of California, Berkeley. It was originally derived from the 6th Edition Unix shell (Thompson shell). Its syntax is modeled after the C programming language. It is used primarily for interactive terminal use, but less frequently for scripting and operating system control. C shell has many interactive commands.

**Korn shell**(1983) is a Unix shell which was developed by David Korn at Bell Labs in the early 1980s and announced at USENIX on July 14, 1983. Other early contributors were Bell Labs developers Mike Veach and Pat Sullivan, who wrote the Emacs- and vi-style line editing modes′ code, respectively. KornShell is backward-compatible with the Bourne shell and includes many features of the C shell, inspired by the requests of Bell Labs users.

**Bourne Again shell**(1989) Brian Fox began coding Bash on January 10, 1988 after Richard Stallman became dissatisfied with the lack of progress being made by a prior developer. Stallman and the Free Software Foundation (FSF) considered a free shell that could run existing sh scripts so strategic to a completely free system built from BSD and GNU code that this was one of the few projects they funded themselves, with Fox undertaking the work as an employee of FSF. Fox released Bash as a beta, version .99, on June 7, 1989 and remained the primary maintainer until sometime between mid-1992 and mid-1994, when he was laid off from FSF and his responsibility was transitioned to another early contributor, Chet Ramey.

**Z shell**(1990) The first version of zsh was written by Paul Falstad in 1990 when he was a student at Princeton University. The name zsh derives from Yale professor Zhong Shao's (then a teaching assistant at Princeton University) name — Paul Falstad thought that Shao's login name, "zsh", was a good name for a shell.

#####3. Why use Zsh?
There are so many feature of Zsh you can do to increase your productivity, while bash is not. Let me show you the awesomeness of Zsh:
 
**Completion**. An example, let's say you want to use cd command, so you type in `cd` on your prompt, but you don't know what you have to do next, let's hit the `Tab` button on your keyboard, see what's happening...

![Alt text](http://i1286.photobucket.com/albums/a601/fauzanqadri/ScreenShot2013-07-11at10624PM_zps960fd88a.png "Completion-1")

in bash it would look like this...

![Alt text](http://i1286.photobucket.com/albums/a601/fauzanqadri/ScreenShot2013-07-11at20703PM_zpsdb3cbd31.png "Bash Completion-1")

Zsh git completion...

![Alt text](http://i1286.photobucket.com/albums/a601/fauzanqadri/ScreenShot2013-07-11at23619PM_zpsd9c79877.png "Git Completion")

![Alt text](http://i1286.photobucket.com/albums/a601/fauzanqadri/ScreenShot2013-07-11at35906PM_zps871dbd67.png "Git Completion-1")

Bash git completion...

![Alt text](http://i1286.photobucket.com/albums/a601/fauzanqadri/ScreenShot2013-07-11at44838PM_zpsda78911c.png "Bash git completion")

okayy...

![Alt text](http://i1286.photobucket.com/albums/a601/fauzanqadri/ScreenShot2013-07-11at44929PM_zpsc8564bb7.png "Bash git a completion")
it's nothing...

it's possible to get completion for git and many other commands in bash by installing bash-completion package, but the completion is still rudimentary compared to Zsh.

1. No cycling thorugh options with repeated tabs
2. No Acompanying info with command, just a list
3. Breaks to new prompt line on each tab instead of updating in-place

There may be ways to improve that situation and bring it more in line with zsh, but with zsh, you get it basically out of the box with a single command in your `.zshrc` to enable completions.


**Zsh Path expansion** here's example how to use path expansion in Zsh, type in `cd /s/l/e` (it's stands for /System/Library/Extensions) on your prompt, and hit `Tab` button, see what will happen...

![Alt text](http://i1286.photobucket.com/albums/a601/fauzanqadri/ScreenShot2013-07-11at53050PM_zps8b4d8541.png "Zsh path expansions")

tadaaaaa.....

![Alt text](http://i1286.photobucket.com/albums/a601/fauzanqadri/ScreenShot2013-07-11at53942PM_zps65438c4b.png "Zsh path expansion-1")

or more impresive...

![Alt text](http://i1286.photobucket.com/albums/a601/fauzanqadri/ScreenShot2013-07-11at54509PM_zps7d32163f.png "Zsh path expansion impresive")

let's see what will happening in bash...

![Alt text](http://i1286.photobucket.com/albums/a601/fauzanqadri/ScreenShot2013-07-11at61154PM_zps0f6c5740.png "Bash path expansion")

hit tab as many as you want, nothing happen...


**Zsh Path replacement** let's say you want to use `cd` command to entering Download folder from your `username` folder, but you're wrong by hitting `Desktop` folder, well, let's replace it by doing somethig like this..

![Alt text](http://i1286.photobucket.com/albums/a601/fauzanqadri/ScreenShot2013-07-11at73039PM_zps42b0979d.png "i was wrong")

whoopss i was wrong...

okey let's replace it...

![Alt text](http://i1286.photobucket.com/albums/a601/fauzanqadri/ScreenShot2013-07-11at73141PM_zpsf858bd7f.png "Zsh path replace")

and it will become like this...

![Alt text](http://i1286.photobucket.com/albums/a601/fauzanqadri/ScreenShot2013-07-11at74115PM_zps2ae13e51.png "Zsh path replace-2")

well, it will become useless if only entering on path, how about you face the situation like this..

![Alt text](http://i1286.photobucket.com/albums/a601/fauzanqadri/ScreenShot2013-07-11at74425PM_zpsfd4d7310.png "Zsh path replace-3")

but you got hit worong path, okey lets replace it...

![Alt text](http://i1286.photobucket.com/albums/a601/fauzanqadri/ScreenShot2013-07-11at74715PM_zps0a38865d.png "usefull")

it will become very usefull right...

now, what will happening if we do this on bash...

![Alt text](http://i1286.photobucket.com/albums/a601/fauzanqadri/ScreenShot2013-07-11at84401PM_zpsb24525ae.png "Bash path replace-1")

OooOoo..

**Zsh Spelling correction** let's say your type in command on your promp, but come on dude we are human...

![Alt text](http://i1286.photobucket.com/albums/a601/fauzanqadri/ScreenShot2013-07-11at85925PM_zpsfa74e0dd.png "Auto Spelling")

**Zsh Aliases**

Normal aliases: 

`alias ls='ls --color=auto'`

Global aliases - apear anywhere in command string

{% highlight sh linenos%}
alias -g gp='| grep -i'
% ps ax gp ruby
#=> ps ax | grep -i ruby
{% endhighlight%}

Suffix aliases - "Open with"


{% highlight sh linenos%}
alias -s rb=vim
alias -s log="less -MN"

% user.rb
#=> vim user.rb

development.log
#=> less -MN development.log
{% endhighlight%}

**Zsh Extend globbing**

![Alt text](http://i1286.photobucket.com/albums/a601/fauzanqadri/ScreenShot2013-07-11at92700PM_zps2ffbdc6e.png "Extend globbing")

`ls **/*.rb`

`**/*.rb` is for rekursif search
![Alt text](http://i1286.photobucket.com/albums/a601/fauzanqadri/ScreenShot2013-07-11at92532PM_zps3a62bb18.png "Extend globbing rekursif")

So, thinking about moving from bash to Zsh ;)