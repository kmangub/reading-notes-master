# Reading Class 3: Git Intro

### Terms

* DVCS (Distributed Version Control System) - Mirrors repositories so people can collaborate together.
* Git - A DVCS that stores data in a filing sytem made up of snapshots. It is very difficult to lose data.

### States

Files in Git can reside in three main states: committed, modified and staged.

* Committed - Save-as
* Modified - Changes are made
* Staged - Files to be committed in the next snapshot

### Cloning Repositories

Cloning repositories are necessary when wanting to edit files from another server, such as GitHub.

You can create a clone of an existing compository by inputting `git clone "url"` in Terminal.

### Status

Enter `git status` and you will be able to see what the status is on the file. 

To make changes you add by entering `git add "file name"`, then you commit by entering `git commit -m "Insert message here"`, then you push by entering `git push origin master`. This process is known as ACP.

[Back to Home Page](README.md)