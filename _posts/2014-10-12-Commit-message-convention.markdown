---
layout: post
title: Commit message convention
date: 2014-10-12
categories: Configuration
---

Every developer has his/her own commit message style. I felt I should use a unique commit message convention so that it will help organize my commits better. 

So after a lot of brain storming I came up with the following style

	[CUDA]{keyword List}<message>

[CUDA]
======

- C is **Create**  (When I create some files in my project)
- U is **Update**/Edit (When something is updated) 
- D is **Delete** (When files are deleted)
- A is **Add** (Adding any external sources like images, documents etc.. to my project)

I will use the letters when these actions are being performed in the commit.
For example if I add a new file and update it with code in a commit that will have **[CU]** at the start of the commit message

{Keyword List}
=============

This keyword list will have the list of important keyword which are relevant to that commit message. 
For example if I am working on my website and I updated the design and added a post to my blog, the keywords can be **Design,1 Post**
So my commit message will be **[CU]{Design, Post}**
I am not defining these keywords as they vary from project to project. 

Message
========

This will include the message related to the commit. It mostly describes what exactly the commit does. 