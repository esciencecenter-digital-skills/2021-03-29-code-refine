# Collaborative Document Day 1
2021-03-29 Code Refinery

Welcome to The Workshop Collaborative Document 
 

This Document is synchronized as you type, so that everyone viewing this page sees the same text. This allows you to collaborate seamlessly on documents. 

All content is publicly available under the Creative Commons Attribution License 

https://creativecommons.org/licenses/by/4.0/ 

 ---------------------------------------------------------------------------- 

* Collaborative Document day 1: [link](https://hackmd.io/@svenvanderburg/Byy93ar4_/edit) 
* Collaborative Document day 2: [link](https://hackmd.io/@svenvanderburg/r1xIRTSNd/edit)
* Collaborative Document day 3: [link](https://hackmd.io/@svenvanderburg/r1UF0prVu/edit)
* Collaborative Document day 4: [link](https://hackmd.io/@svenvanderburg/rkocCTHV_/edit)
  

## 👮Code of Conduct 

* Participants are expected to follow those guidelines: 
* Use welcoming and inclusive language 
* Be respectful of different viewpoints and experiences 
* Gracefully accept constructive criticism 
* Focus on what is best for the community 
* Show courtesy and respect towards other community members 
 

## ⚖️ License 

All content is publicly available under the Creative Commons Attribution License: https://creativecommons.org/licenses/by/4.0/ 

 

## 🙋Getting help 
to ask a question, type `/hand` in the chat window 

to get help, type `/help` in the chat window 

you can ask questions in the document or chat window and helpers will try to help you 
 

## 🖥 Workshop website 

https://escience-academy.github.io/2021-03-29-code-refine/


🛠 Setup 
https://escience-academy.github.io/2021-03-29-code-refine/#setup

🗓️ Full schedule
https://escience-academy.github.io/2021-03-29-code-refine/#schedule
 

## 👩‍🏫👩‍💻🎓 Instructors 

Sven van der Burg, Jens Wehner
 

## 🧑‍🙋 Helpers 

Djura Smits, Alessio Sclocco
 

## 🗓️ Agenda 

* 09:00	Welcome
* 09:30	Introduction to version control with Git
* 10:45	Coffee break
* 11:00	Introduction to version control with Git
* 12:00	Coffee break
* 12:15	Introduction to version control with Git
* 12:45	Wrap-up
* 13:00	END
 
 

## 🧠 Collaborative Notes 

### 🦸‍♂️ Exercises

#### Users
How do you work on your projects? How do you save intermediate results? How do backup your projects?
* Aafke: google docs (or send around the document) webdrive/surfdrive (shared folders)
* Judith: version control Overleaf, shared documents in Teams, github, external harddiks for backups
* Bouke - teams document (blegh), google drive, onedrive
* Anne Fleur - yyyymmddNameDoc, backup overleaf, google docs, email to self, etc
* Banafsheh - Google docs, github, Overleaf, shared folder on cartesius
* Wietske - folders, latex (overleaf), git, powerpoint/slides, email to supervisors
* Eef - Word (one drive), Google drive/docs 
* Dirk-Jan - combination of google docs, folders, gitlab, email, onedrive
* Tareq - google drive, github
* Mark - Collaboration in Google Docs & Slack, personal projects look like ...rev2_final_goodnow.py, backups on local harddisk and on surfdrive. 
* Sandra - Google drive, OneDrive, Overleaf, gitlab, chaos...
* Dario - GitHub, Google Drive, Dropbox

### Which command(s) below would save the changes of myfile.txt to my local Git repository?

1. $ git commit -m “my recent changes”
2. 
    - $ git init myfile.txt
    - $ git commit -m “my recent changes"
3. 
    - $ git add myfile.txt
    - $ git commit -m “my recent changes”
4. $ git commit -m myfile.txt “my recent changes”
    
* Aafke: 3
* Judith: 3
* Bouke: 3
* Anne Fleur - 3 
* Banafsheh 3
* Wietske 3
* Eef 3
* Dirk-Jan - 3
* Mark: 3
* Omar - 3
* Sandra - (4 is invalid syntax; 3 valid; 2 forgot to add; 1 forgot to add)



### Committing Multiple Files

The staging area can hold changes from any number of files that you want to commit as a single snapshot.

Add some text to mars.txt noting your decision to consider Venus as a base
Create a new file venus.txt with your initial thoughts about Venus as a base for you and your friends
Add changes from both files to the staging area, and commit those changes.


* Aafke
* Judith
* Bouke
* Anne Fleur
* Banafsheh 
* Wietske
* Eef
* Dirk-Jan
* Mark
* Omar

### Break 1 10:45 - 11:00

### Recovering Older Versions of a File
Jennifer has made changes to the Python script that she has been working on for weeks, and the modifications she made this morning “broke” the script and it no longer runs. She has spent ~ 1hr trying to fix it, with no luck…

Luckily, she has been keeping track of her project’s versions using Git! Which commands below will let her recover the last committed version of her Python script called data_cruncher.py?

1. `git checkout HEAD`
2. `git checkout HEAD data_cruncher.py`
3. `git checkout HEAD~1 data_cruncher.py`
4. `git checkout <unique ID of last commit> data_cruncher.py`
5. Both 2 and 4

* Aafke: 5
* Judith: 5
* Bouke: 5
* Anne Fleur
* Banafsheh 5
* Wietske: 5
* Eef 5
* Dirk-Jan - 5
* Mark: 5
* Omar 5
* Dario
* Sandra - 5


### Reverting a Commit

Jennifer is collaborating on her Python script with her colleagues and realizes her last commit to the project’s repository contained an error and she wants to undo it. git revert [erroneous commit ID] will create a new commit that reverses Jennifer’s erroneous commit. Therefore git revert is different to git checkout [commit ID] because git checkout returns the files within the local repository to a previous state, whereas git revert reverses changes committed to the local and project repositories.
Below are the right steps and explanations for Jennifer to use git revert, what is the missing command?

1.     ________ # Look at the git history of the project to find the commit ID
2.  Copy the ID (the first few characters of the ID, e.g. 0b1d055).
3.     git revert [commit ID]
4. Type in the new commit message.
5. Save and close

* Aafke: git log
* Judith: git log
* Bouke - git log
* Anne Fleur - git log
* Banafsheh - git log / git commit -m ¨¨/ 
* Wietske git log --oneline
* Eef
* Dirk-Jan `git log --online`
* Mark: git commit -m "Undone commit [erroneous commit ID]"
* Omar: git log --oneline / 
* Dario
* Sandra - `git log --oneline`
* Siri: git commit -m "removde this and that"

Solution:
```bash=
git log --oneline
git revert <commit id>
git log --oneline
# Text editor will open

git log --oneline
```

### Understanding Workflow and History
What is the output of the last command in
```
$ cd planets
$ echo "Venus is beautiful and full of love" > venus.txt
$ git add venus.txt
$ echo "Venus is too hot to be suitable as a base" >> venus.txt
$ git commit -m "Comment on Venus as an unsuitable base"
$ git checkout HEAD venus.txt
$ cat venus.txt #this will print the contents of venus.txt to the screen
```
1. Venus is too hot to be suitable as a base
2. Venus is beautiful and full of love
3. Venus is beautiful and full of love  
   Venus is too hot to be suitable as a base
5. Error because you have changed venus.txt without committing the changes


- Q: What is the difference between > and >> in the question?
- A: > is to overwrite, >> is to append to the file

* Aafke: 2
* Judith: 2
* Bouke: 2
* Anne Fleur
* Banafsheh 2 
* Wietske 2
* Eef 2
* Dirk-Jan: 2
* Mark: 2
* Omar: 2
* Dario
* Sandra - 3

A: 2

#### Break, we'll be back at 12:19
Tops:
* Nice pace
* Really nice admosphere, interactive, this document is nice!
* Working together in this document is nice! 
* Nice teaching atmosphere, active workshop 
* I liked the collaborative document. 

Tips:
* Stick maybe a little bit more to content and shorter on questions, so everybody stays focussed
* We had some questions to which first the answer was: "That's not important for now" and then the questions were still eloborately discussed for multiple minutes.

### 🧑‍💻 Command Log
Check if you have git installed:
```bash=
git
```

Create a git repository:
```bash
mkdir planets
cd planets/
git init
# Initialized empty Git repository in ....
ls -a
# You'll find a hidden folder called .git

git status
# On branch master ...
```

Let's create some data:
```bash=
nano mars.txt
# Enter some text and exit editor

# Check content of your file:
cat mars.txt 
```

Add your file to version control:
```bash
git status
git add mars.txt
git status
git commit -m "Start notes on Mars"
```

Configure git:
```bash=
git config --global user.name "your name"
git config --global user.email "your@email.com"

# Note: you might want to omit --global, like this
git config user.name "your name"
git config user.email "your@email.com"
```

Try committing again, this should work now:
```bash=
git commit -m "Start notes on Mars as a base"

git status
```

Check what has happened in your repo:
```bash=
git log
```
Edit your file:
```bash=
nano mars.txt
# Then enter some more text
# ctrl-o ctrl-x to exit

cat mars.txt
git status

# Check the difference between current state and last commit:
git diff
```

For windows users, additional configuration:
```bash=
git config --global core.autocrlf true
```

Check git version:
```bash=
git --version
```

Commit our change:
```bash=
# Add file before commit
git add mars.txt
git commit -m "Added info about two moons"

# If you want to edit the text in an editor:
git commit

# Git log will show two commits
git log
```

Let's add a bit more:
```bash=
nano mars.txt

# Enter some text, ctr-o ctrl-x

git diff
git add mars.txt
git diff

# Git diff shows nothing now

# To check changes that have been staged:
git diff --staged

git commit -m "Discussed humidity"
git status
```

```bash
git log

# Log shows 3 commits

# Log with one line per commit
git log --oneline

# Graph visualization
git log --oneline --graph
```

Create subdirectory:
```bash=
mkdir spaceships

git add spaceships

git status

# Folder will not be listed

# Make sure empty folder is added
cd spaceships/
touch .gitkeep

git status
# Folder will be listed
```

```bash=
nano mars.txt
# Add some text

nano venus.txt
# Also add some text
```


```bash=
git add mars.txt venus.txt
git status
git commit -m "Added info for venus and updated mars"
# 2 files changed, etc..
```

```bash=
git log --oneline
nano mars.txt

# Compare files to latest commit:
git diff HEAD mars.txt

# Look at second latest commit
git diff HEAD~1 mars.txt

# Look at an older commit:
git show HEAD~2 mars.txt
```
```bash=
git diff HEAD~3 mars.txt
git log --oneline

# You can use commit identifier instead of HEAD:
git diff <commit code> mars.txt
git show <commit code> mars.txt

# If you don't specify file it will show diff for all
git show HEAD
```

Renaming a file:
```bash=
mv venus.txt aphrodite.txt
git status

# Git will say venus.txt is deleted, aphrodite.txt is untracked
git add venus.txt aphrodite.txt
git commit -m "renamed venus to aphrodite"
git status
git show HEAD

# Better suggestion
git mv aphrodite.txt venus.txt
git commit -m "renamed ...."
```

```bash=
git status
# Mars is modified but not added

cat mars.txt
# Restore old version
git checkout HEAD mars.txt

cat mars.txt
# Last change is gone
```

Check out older version:
```bash=
git log --oneline
# Pick commit id

git checkout <commit id> mars.txt
git status

git reset HEAD mars.txt
# Last change isn't staged anymore


cat mars.txt
git checkout HEAD mars.txt
```

Detached HEAD state:
```bash=
git checkout <commit code>

# Get back by checking out master branch again
git checkout master

git status
```

Reverting:
```bash=
git log --oneline
git revert
```

Github:
* go to repositories
* Click on "new"
* Give repo a name
* Add description
* Tick either public or private
* Do not tick any of the checkboxes at the bottom
* Click create repository

Push an existing repository from the command line
```bash=
git remote add origin <git repo url>
git branch -M main
git push -u origin main

# Fill in login prompt with your github credentials
# Code is pushed to github

git branch
# This will now show "main" as only branch
```

Get remote changes:
```bash=
git pull

cat mars.txt
# mars.txt will show remote updates
```

```bash=
nano mars.txt
# Add something to the file

git add mars.txt
git commit -m "Wrote thanks"

git log --oneline
# Local main is further than origin/main

git push
# Now changes are pushed to remote
```



------ end of the command log

### ❓🤔 Questions (put down non urgent questions, our helpers and instructors will answer them)
* Q: How do I get a certificate of attendance?
    * A: Send an email to training@esciencecenter.nl
* Q: Do we talk about git large file storage as well?
    * A: No, sorry.
* Q: Will we address branching and merging today?
    * A: That is part of Day 2.
* Q: What can I do if "$ git config --global core.autocrlf true" is not working (windows, anaconda).
    * What does it say?
    * It still shows the removal of the line where the newline is inserted. And insertion in the diff. Like this:  
        ```Two moons are problematic
        -but it is not very humid
        \ No newline at end of file
        +but it is not very humid
        +The color is red-like
        +It is round
        \ No newline at end of file
        ```
    * A: In the terminal, do: `nano mars.txt` and edit the file there
    * It could be that you still have a 'windows-style' line ending in the file. Maybe you can try editing the file again?
    * Or try:
      ``` 
      git config --global core.eol lf 
      git config --global core.autocrlf input
      ```
* Q: I can't type my password when logging in to git on command line
    * A: Command line will not show your password

## 📚 Resources 

 