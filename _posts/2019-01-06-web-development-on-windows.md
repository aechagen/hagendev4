---
layout: posts
title: Web Development Environment on Windows
date: 2019-01-06
categories: [life]
# published: false
header:
  image: /assets/images/laptop-desktop.jpg
---

In honor of the new year, I decided to re-install Windows on my laptop - It's sort of a "New Year, New Me" deal for my computer. I had only done a couple times before, both times being within the first few months I purchased my Surface Pro 2017 back in August last year. Despite the rocky start, I stuck with it, and I've enjoyed every minute of using my laptop for every task I throw at it, from coding to my online classes, to even running chess engines and doodling with One Note. But I digress. 

This aim of this post is to show how got my web development environment up and running for the new year. I haven't seen very many tutorials on the subject, so I hope I can bring something new to the table. 

## Installing Linux on Windows

The first step, regardless if you've got a newly installed OS or not, is to install Linux on your current Windows OS. I just followed the steps from [https://aka.ms/wslinstall](https://aka.ms/wslinstall). TL;DR? Open up Powershell by right-clicking the Windows start icon and clicking "Windows Powershell (Admin)" and enter the following command:

```
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
```

Next, head over to the Windows store and pick your favorite flavor of Linux. I chose Ubuntu because I've worked with it before. Follow the steps to install, launch Ubuntu and set up a username and password for sudo. Congratulations, you've installed Linux on Windows! 

## Code Editors on Code Editors on Code Editors

There are a ton of different code editors out there. When I first started out learning to code, I used [Sublime Text](https://www.sublimetext.com/) religiously. Since then, I've dabbled with [Atom](https://atom.io/) and [Brackets](http://brackets.io/), but I've finally landed on [Visual Studio Code](https://code.visualstudio.com/), and I couldn't be happier. You can pick whichever you're the most comfortable with, but for this post, I'll be going over VS Code. 

Head over to the [Visual Studio Code website to download](https://code.visualstudio.com/). Juggling two operating systems might be a little confusing, but you want to install the Windows version.. It's easier that way. 

## Git for Windows

Download Git for Windows [here](https://git-scm.com/) and follow the prompts to install. Here are some of the options I changed:
- Checked "Don't create a Start Menu folder"
- Checked "Use VIM as Git's default editor"
- Checked "Use Git from the Windows Command Prompt"
- Checked "Use the OpenSSL library"
- Selected "Checkout as-is, commit Unix-style endings"
- Seleceted "Use Windows default console window"

## Using Bash with VS Code

The last piece of setup with VS Code we'll do is setting the default terminal to Bash. To do this, just open File -> Settings and add this rule:

```
"terminal.integrated.shell.windows": "C:\\Windows\\System32\\bash.exe"
```
Reload VS code and activate the terminal with CTRL + `. Alternatively, you can search "Integrated Terminal" in the Command Palette.

## Install Git, Node, Ruby and Jekyll

I know what you're thinking. "I just installed Git!" .. Well, you're right. We installed Git for Windows, now we need to install it on our Linux distro so that we can use Git from inside Bash. 

```
sudo apt install git
git config --global user.email "you@email.com"
git config --global user.name "Your Name"
git config --global core.autocrlf input
```

In addition to this, you'll want to make sure to add an [SSH key](https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/#platform-linux) to Github using the Linux instructions. 

## Installing Node

Another easy install.

```
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.9/install.sh | bash
source ~/.bashrc
nvm install --lts
```

## Installing Ruby and Jekyll

To keep it short and sweet, I followed the instructions on the [Jekyll website](https://jekyllrb.com/docs/installation/windows/) to install Ruby and Jekyll. If you don't use Jekyll or Ruby at all, feel free to stop there.

## And That's It!

Hopefully this helped out a little bit with getting your new environment up and running. When I first made the switch to Windows from the usual Mac environment for development last year, I was skeptical, but I've enjoyed every minute of the transition. I can't wait to continue learning about the web in 2019!