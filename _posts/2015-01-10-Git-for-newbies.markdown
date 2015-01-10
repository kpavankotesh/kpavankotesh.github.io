---
layout: post
comments: true
title: Git for Newbies - Part 1
date: 2015-01-10
categories: 4Newbies
---

Git is a Version control System. Lets say you are writing your resume. You might want to make different versions for different companies/ different job applications with lots of similar content(almost 80%) in each of them. So you will have to create multiple documents with almost 80% of them is same content! That's where git helps you. It will instead let you create only one document and remembers just the changes made in the different versions. This way we save lot of space and easy to manage data. Not only this, there are lot of other awesome aspects of git. 

Terms you should understand before we move further: 

- **Git** - It is the software you install in your local computer to manage everything
- **Github/Bitbucket** - It is the repository where we store our code or content over the internet, so that we can share and save our co
- **Remote** - URL or the address of the repository where store the content over internet
- **Local** - Your local computer

Set up
------
- [Install Git](http://www.git-scm.com/downloads) in your computer
- Register for One of the hubs to store your content online ([Github](https://github.com/) / [Bitbucket](https://bitbucket.org/))
- That's it!

How everything works?
---------------------

Lets start with a sample project where we will experiment with git. 
Create a folder(Name it Project1) and add two text files to it(one.txt, two.txt). Now go to terminal and cd to the Project1 folder. So we are in out project folder now. 

First of all we need to initialize git in our project. So type the follwing command: 

	git init

This will create a .git folder with some files inside it. Now all the git commands will work in this project folder. Try this to get the current status of the project folder
	
	git status

Git is ready to start tracking what ever you want it to track. Now the two files one.txt and two.txt are in Untracked files section. You need to specifically mention to git that it need to track a specific file or folder. so do this

	git add one.txt
	git add two.txt

Now git started tracking the two files. From now git will recognize what ever changes you make to your file. Now when you check *git status* you will see the files in **Changes to be committed:** section. This means, git now recognized all the changes you made to your project and it is ready to remember them permanantly. Now just open one.txt and type something ("This is my first line"). 

Now try *git status*. You should see *modified:   one.txt* in the  **Changes not staged for commit:** section. This means the changes you made are not recognized by git yet. So you will have to do following again

	git add one.txt

Now git remembers all the changes you made in the one.txt file. Now we commit all the changes. You can think a commit as naming a particular set of changes in the project.

	git commit -m "Some message explaining what "

Try *git log* to check your history. It will show you your first commit. 
Now you need to send this whole content to the github/bitbucket project. To do that you need to create a new repository in your github account and get the HTTP URL. The url looks something like *https://github.com/username/projectname.git*. We need to tell our local project to this send content to this repository. So we need to add remote address to our project

	git remote add origin https://github.com/username/projectname.git

Type *git remote -v* to confirm you have successfully added the remote address to your project
Now we need to send our commits to remote repository. 

	git push -u origin master 

Type your username and password of github/bitbucket when prompted. Then it pushes the whole content to remote repo. That's it! Now you have your repository on github and you can take it anytime, anywhere to any computer and start working on your project. You need not to carry your project everywhere you go. 
To get the project you just need to clone your project from your remote url 

	git clone https://github.com/username/projectname.git

Now you have your project setup on your new environment and you can make necessary additions and commit your changes and push it back to github! 
