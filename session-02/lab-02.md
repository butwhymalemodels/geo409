# Module 02: Setting up a modern mapping workflow: Brackets & Git
## Overview
In this lab we will do the following:

* Install Brackets (an text editor) and Github (a version control system)
* Get to know the 'git' workflow. This includes:
    * Creating repositories
	* Adding & changing files
	* Making & reverting commits
	* Syncing with remote (github.com) repositories

## Introduction
As almost all the software involved in a modern web mapping workflow is, in one way or another, text-based, the essential tools for a web mapper revolve around making handling these text files as easy as possible. In this course we will make heavy use of two specific programs.

First, **Brackets** is a free and open-source text editor for working with code and design. It has a number of features that you’ll come to love such as code syntax highlighting (to make code more legible), auto-complete (for when you don’t want to type or remember that long variable name), and live preview (so you can visually see how your code would be rendered in the browser).

Second, there is **git and Github**. Git itself is — with a fancy name — a distributed version control system. It basically records changes to the various files in your project (a repository, in git speak) as it progresses. This allows you to track different versions and, if (or when!) you mess up, go back to a previous version. **This. Is. HUGE!** Say you’re working on a term paper in Microsoft Word: normally you would perhaps save different version under different names — termpaperV1.docx; termpaperV2.docx; termpaperFinal.docx; termpaperReallyFinal.docx.

With git, you even only ever have one filename -- e.g ‘termpaper.docx’ -- but you save different versions as snapshots in time. It’s a little difficult to wrap your head around — but don’t worry, it will become second-nature once you’re through with this lab. The other big advantage of git is its close integration with Github. Github is a website that provides a platform to share your git repositories. This is very powerful as it allows other people to collaborate with you on the same repository and you can even share your projects with the larger public via open webpages. During the course, you will also use this mechanism to submit and share your assignments with your instructors.

## Installing Brackets
If you’re working only on the computers in this lab, Brackets already comes pre-installed. If you prefer your own laptop, you can download a copy of Brackets for either Mac or Windows from [http://brackets.io/](http://brackets.io/). Make sure you download the version *without* Extract.

![](assets/Screenshot%202015-01-19%2011.48.57.png)

## Setting up an account at Github
To get started with Github, you first need to create an account.  Signing up is very easy. Navigate to [https://github.com/](https://github.com/) and sign up with a username, password and email address. **Make sure you use your @uky.edu address as you need it for the next step.**

![](assets/Screenshot%202015-01-19%2011.51.06.png)

Github is free to use but it also has paid plans. These paid plans offer the possibility of making repositories private instead of public. This is very helpful while we’re still learning as we don’t want our stumbles and ugly code to be visible to the entire world. Later on, this might also be useful if you’re doing work for a client and want to share a draft that you don't want to share with the wider world.

A really good thing is that Github provides this service of private repositories free-of-charge to students. Once you’re signed-up, go to [https://education.github.com/](https://education.github.com/) and click on the 'Get the Pack' button. It includes access to Github private repositories as well as a bunch of other cool stuff. Sign in with your Github account (if you haven’t done so already) and follow the instructions. Github will ask for a copy of your student ID or an academic transcript to verify your status. You can get the latter through myUK directly. Once you’ve submitted it might take a while to get approved, but we can get started without a problem in the meantime!

![](assets/Screenshot%202015-01-19%2012.13.46.png)

## Download Github for Mac/Windows and basic configuration
Depending on your operating system, you can now download the Github software from either [https://windows.github.com/](https://windows.github.com/) or [https://mac.github.com/](https://mac.github.com/). Remember, you only need to install this software if you’re working on your own computer — it’s already installed on the lab’s computers.

Once downloaded, open Github and it will ask you to walk through some configuration steps. This is where you fill out the account username and password you created earlier.

![](assets/Screen%20Shot%202015-01-19%20at%2012.21.42%20PM.png)

In the second screen, you will be asked to supply your name and email. Please make sure your real name is used here — so that your colleagues & instructors can actually identify you.

![](assets/Screen%20Shot%202015-01-19%20at%2012.22.40%20PM.png)

Once the configuration is successful, you should see an empty Github window and we’re finally ready to roll.

![](assets/Screen%20Shot%202015-01-19%20at%2012.22.54%20PM.png)

## Creating a new, empty repository and ‘committing’ files
A Git repository is nothing more than a directory that houses all of a project’s files. Click the little ‘+’ icon in the upper left corner to create a new repository. You’re free to give it any name — here we use ‘my-cool-new-project’. During this course, *we will keep all of our files together on your USB drive so make sure you select that location under ‘local path’*.

This is KEY. Keeping track of your files is extremely important. As the Buddha once said, "Only those with good file structure will acheive Nirvana. And I'm not talking about the grunge band." 

![](assets/Screenshot%202015-01-19%2012.35.05.png)

You now have a new Git repository. Sadly, it’s nothing more than an empty directory at this point so let’s change that. Open Brackets and go File | Open Folder and choose the repository folder you just created. You’ll see two ‘.git’ files in the left pane that we will just ignore for now. Just right-click in that pane and select ‘New File’. Let’s call the file ‘mynotes.txt’. Once created, type a sentence or two in your text file:

![](assets/Screenshot%202015-01-19%2016.57.23.png)

Switching back to Github, you will see that it has now detected the new file and ‘staged’ that file under the ‘Uncommitted changes’ heading. The *commit* is a central part of how a git repository works. Until we actually commit our changes, git doesn’t really know about them yet. Basically, a commit bundles anything that has changed up until that point together and creates a snapshot in time. It creates a version of your entire project at that very point in time. Each commit then becomes an individual snapshot that you can, in case of dire emergency, go back to later on. 

You will see how this works in a bit — for now, let’s *commit* our new file to the repository. Each commit must always have a little summary (the small text box with the "Added a file with notes" text) — and if you are so inclined you can add a longer description. Think about how you would normally number the versions of your term paper. In this case, we don’t have to restrict ourselves to a number. Instead, we can use descriptions like ‘Wrote introduction’; ‘Added bibliography’; or ‘Rewrote entire paper after professor destroyed my hopes and dreams’ and so forth. Add a summary and commit your change:

![](assets/Screenshot%202015-01-19%2017.07.12.png)

Now that our file is safely inside of the repository, let’s change its contents a bit and see what happens:

![](assets/Screenshot%202015-01-19%2017.08.55.png)

Once you make a change to the text and save the file in Brackets, you’ll notice that Github picks up on that change right away. In the right panel, it gives a clear insight into what exactly changed. In git-speak, this is called a ‘diff’ — really just showing the difference between two version of the same file. Lines with a small ‘-‘ have been deleted and those with a small ‘+’ have been added. Key additions/removals are indicated by green and red colors. Write a small summary again and commit this change to your repository as well.

![](assets/Screenshot%202015-01-19%2017.09.59.png)

## Commit history and reverting changes
The great thing about writing these little summaries is that we can get a clear sense of what went on in our project each step of the way. Go to the ‘History’ tab and have a look:

![](assets/Screenshot%202015-01-19%2017.13.19.png)

Let’s say we regret the last change we made and want to revert back to the previous state. All it takes is navigating to the specific commit that we'd like to return to. Then right-click on the little cog and choose ‘roll-back’.

![](assets/Screenshot%202015-01-19%2017.17.14.png)

You will see that even this roll-back is turned into a commit in and of itself. This might seem confusing but it allows you to cancel the roll-back if you change your mind yet again. How meta! You can double-check your roll-back in Brackets: you should see your text document back in its initial state!

## Github and remote repositories
When you go back to the ‘Changes’ tab of your repository, you will see that all of our commits so far are ‘unsynced’. This is because git has two types of repositories: local and remote. The local repository is what we just created. It lives on your own hard drive or, in this case, USB stick. Seriously, remember what the Buddha said about Nirvana. **Keep track of your files!!**

The remote repository is a copy of our repository on the internet, in this case on the Github.com platform. This is what allows us to put our projects online on Github, collaborate with other people as well as provide a safe backup location.  

To sync your local repository to github.com, click the ‘Publish’ button in the upper-right corner. Note, it says publish right now since you are creating a new project. Once you have the project published, the button will say Sync. 

![](assets/Screenshot%202015-01-19%2017.26.28.png)

Once it’s done syncing, you can now go to github.com/username/my-cool-new-project/ to visit the online version of your repository.

![](assets/Screenshot%202015-01-19%2017.28.09.png)

Just think of it. You have your local copy of your files on your USB stick and a second identical copy (assuming you are syncing) on the Internet.  Wozzers!  That's what we call security.

It also reminds us of a bad joke. The Devil and Jesus were both coding a new web map. They spent hours working on it when all of a sudden the power went out. The Devil was furious!! He yelled and cursed and kicked things over. "I lost all of my code!". In constrast Jesus just sat there and hummed a little tune while waiting for the power to come back on. Enraged by this Zen calm, the Devil demanded to know why Jesus wasn't upset. Jesus just smiled and said, "Jesus saves."

Of course, in this course, Jesus would have said, "Jesus uses Github" but that's not as good of a punchline. Not that the real punchline is all that great either.

## Branching, Merging, Cloning and Forking: The Four Horsemen of the Github 

There are two important functionalities of git repositories that we still need to discuss. The first is *branching and merging*. You can create a new branch within a project if you want to explore or try out, say, a new design idea. Or you want to add some functionality to your map but don't know exactly if it's going to work out. Git allows you to create a separate branch to explore these things -- you will still make commits but they apply only to the specific branch and not the main project ('master' branch in git-speak). If your idea doesn't work out after all, you can just delete the branch in one fell swoop instead of reverting dozens of individual commits. If your idea does work out (of course it did!), you can merge your branch back into 'master'. This is also very useful if you work on different parts of the project with multiple people: everybody can work on their own bit in a separate branch without interfering too much with all the other work going on. Further into this course, when our mapping projects start to get more complex, this will be a useful feature but for now its enough to know of its existence.

The last functionality that we need to discuss is cloning and forking. Until now we have only ever created new repositories *locally*. However, if you browse github.com you notice that there are literally thousands of pre-existing projects. Sometimes you find an interesting repository that you'd like to use as a starting point -- or perhaps dissect in more detail on your own computer. You can do so by *cloning* a repository on your own computer. After you have installed the Github software, you will notice that each repository that you visit on Github.com has a 'Clone in Desktop' button in the right panel. Clicking that will create a local copy of that repository -- with all of its code -- in the location you specify. There's only one downside: if you want to make changes, you can do so but you cannot necessarily sync those commits back to the remote repository. The reason is simple: if anybody could make changes to everything, projects would start to get really messy fast.

This is why you can also *fork* a repository. Forking creates a carbon-copy of repository into your own account. For example, if you like the project at github.com/atepoorthuis/my-cool-new-project, you can fork it and a copy would then live at github.com/YOURUSERNAME/my-cool-new-project. Once you clone this forked repository to your local machine, you can actually sync your changes and commits just fine. That's because you are now working on a copy of the project that is owned by yourself!

## Homework: Task A

1. Fork [https://github.com/newmapsplus/geo409](https://github.com/newmapsplus/geo409)
2. Clone your newly forked repository to your USB drive
3. You will see that there's only one directory 'module-03' with a single file in it -- 'index.html'. This is the starting point for the next lab. For now, we're going to make small change to practice our git workflow. As you will be submitting this as an assignment (Task A). Let's go ahead and copy the 'module-03' directory and all its contents to directory called 'task-a' so that you now have two directories with the same index.html file.

![](assets/Screenshot%202015-01-20%2012.55.40.png)

4. Open the task-a/index.html file in Brackets and add your name in the appropriate location. Also update the coordinates of the center of the map to those of Lexington, KY. After saving the file in Brackets, you can double-check your work by opening the index.html in Chrome.
5. Commit these changes and sync your local repository to github.com
6. Submit the url of your repository in this assignment

**Definitions**
* Git: A (distributed) version control system that allows you to manage (and revert) changes to (text) files.
* Github.com: An online platform, built on top of Git, that allows for online collaborating and sharing of Git repositories
* Github Client: A program that allows for the management of git repositories through a graphical user interface (instead of command line)

**Various git terms**
* Repository: A directory containing all of a project's files, managed by the git workflow
* Commit: A specific snapshot of a project's files
* Revert: Undoing one (or more) commit, basically returning back to a previous saved version of a project
* Clone: A copy of a remote repository to a local machine
* Fork: A carbon-copy clone of another person's remote repository to one that's owned by yourself
* Remote repository: A git repository that exists on a remote server, most often the github.com platform
* Branch: A specific *context* of a repository. Often used to work on a specific feature or new idea
* Merge: Branches can be merged back into the main branch. This brings all the commits made on a specific branch into the main context of the project. E.g. if a certain feature proves useful it can be added to the main project at that time.