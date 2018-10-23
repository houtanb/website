---
layout: post
title: Setting up a Mac for Scientific Computing
date: 2018-07-05
description: Scientific Computing on macOS
summary: Notes to myself about how to setup a new Mac
---

# Scientific Programming on a Mac

## References

Sourabh Bajaj has spent a lot more time outlining his setup than I have. I'd encourage you to look at his page because it's a valuable resource.

## Emacs
I use [Gnu Emacs For Mac](https://emacsformacosx.com/)
My very simple, fast-loading [emacs config](https://github.com/houtanb/emacs-config)

## Terminal
I used [this modification](https://www.macworld.com/article/1146015/os-x/termhistory.html) to my `.bashrc` file to allow me to type in part of a command and then press the up/down arrow to search through the history for commands beginning with that part (as in the Matlab command line)
Directly from the website (in case it goes anywhere...)

Add these two lines to the file, but note you can't copy and paste these lines, as there are special characters in there (which I'll explain how to enter).
```
    bind '"^[[A":history-search-backward'
    bind '"^[[B":history-search-forward'
```
The special characters are represented by the `^[[A` and `^[[B` bits on each line. These are, respectively, the Up Arrow and Down Arrow keys. So how do you type them in nano?

Copy and paste the first part of each line above (`bind '"`), and then press Escape-V. When you do, you'll see a little tag at the bottom of the window that reads `[ Verbatim Input ]`. Now press the Up Arrow (or Down Arrow, depending on the line), and you'll see the above codes appear (and you'll exit Verbatim Input mode when you press the arrow key). After that, just copy and paste the rest of each line, and you're done.

## Finder
I like having the current path in the Finder title bar. If you like it, run the following at the terminal prompt:
```
defaults write com.apple.finder _FXShowPosixPathInTitle -bool true; killall Finder
```

## Package Manager
[Homebrew](https://brew.sh/) provides simple downloads of open source software that isn't included in XCode (e.g., `gfortran`) or by default on macOS.

## Other Useful Programs
[Spectacle](https://www.spectacleapp.com/)
[Karabiner](https://pqrs.org/osx/karabiner/)
[KeyRemap4MacBook]()
Git (also, see [my git handouts](/git))
I used to use [GitX-dev](http://rowanj.github.io/gitx/) (a fork of the apparently defunct [GitX](http://gitx.frim.nl/)) as a simple, light-weight Git GUI to visualize the git history (I issue all commands from the command line). As it is rather buggy os 10.12, I have switched to [Fork](https://git-fork.com/), which is not as good but is the best/simplest GUI I was able to find. SourceTree just has too much going on for me.

## Software distribution on a Mac
I use [Packages](http://s.sudre.free.fr/Software/Packages/about.html) to create the Dynare macOS installer package.

What follows is older and outdated for newer versions of macOS
PackageMaker does what it sets out to do but is poorly documented, leaving the user to feel around for himself. This is especially true of its command line options, which become fairly important if you intend to automate the package-making process. After a bit of searching, I found several very useful links that make using PackageMaker far less inscrutable, though it's still not quite a pleasure :) Now, it would be wonderful if you could actually set GUI values from the command line (eg title, license, background image). Or, if that's already possible, I'd love to know how to do it :)

[Description of command line arguments for PackageMaker](http://www.manpagez.com/man/1/packagemaker/)

[Very useful guidance for automating the creation of a .dmg file I didn't end up going with this, but it's quite useful](https://stackoverflow.com/questions/96882/how-do-i-create-a-nice-looking-dmg-for-mac-os-x-using-command-line-tools)

[In general, the software and tutorials on this page are quite good](http://s.sudre.free.fr/Packaging.html). Specifically, the program Packages seems like a good replacement for PackageMaker and the documentation is more straightforward

## Scheduling Tasks
It seems like `cron` works on macOS now, so no need to fiddle with `launchd`!

What follows is older and outdated for newer versions of macOS
Cron v Launchd: the "new mac" way is to use launchd now that cron has been depricated. In this case, the Linux/Mac stereotypes have been reversed. Launchd is less straightforward to use than a crontab, but is far more versatile allowing you to run a job as a different user without modifying a shell script. The toughest thing is creating your Launchd plist, but luckily there are some really nice people out there that have spent the time to demystify it

[Really great resource to learn the Launchd plist basics](https://alvinalexander.com/mac-os-x/launchd-examples-launchd-plist-file-examples-mac)
Once you've gotten the gist of it, use the man page to customize it to your need (you can get the same info by typing `man launchd.plist` at the terminal prompt)

## Dvorak
After having had RSI problems with my wrists and forearms, I made the switch to a Dvorak keyboard layout (System Preferences...-> Language & Text -> Input Sources -> Search for Dvorak). Though I made the switch without any typing lessons (I just printed out the keyboard map, and struggled with it for a while...even, quite dorkily, walking down the street, saying a letter and moving the associated dvorak-finger to overwrite my qwerty muscle memory), you don't have to! Here's a great [dvorak typing](http://gigliwood.com/abcd/lessons/) lesson website, that'll take you back to your 6th grade typing class :)

[Good Dvorak Resource](http://www.mit.edu/~jcb/Dvorak/)

## Keyboard Bindings
I followed the advice on this site for rebinding my caps lock key to be used as a key modifier for use with [Slate](https://github.com/jigish/slate) and for binding the shift keys to left and right parenthesis when not used with another key.
