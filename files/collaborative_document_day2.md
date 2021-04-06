# Collaborative Document Day 2
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
 

## 👩‍🏫👩‍💻🎓 Instructors 

Sven van der Burg, Jens Wehner
 

## 🧑‍🙋 Helpers 

Djura Smits, Alessio Sclocco
 

## �️ Agenda 

* 09:00	Welcome
* 09:15	Collaboration with Git and GitHub
* 10:15	Coffee break
* 10:30	Collaboration with Git and GitHub
* 11:30	Coffee break
* 11:45	Collaboration with Git and GitHub
* 12:45	Wrap-up
* 13:00	END
 
 

## 🧠 Collaborative Notes 


### :notebook_with_decorative_cover: Exercises

#### Exercise: Working as a project collaborator

- Log into Github and create a new repository
- Make the repository public
- clone it to your desktop
- add some code
- push the changes to the repository
- Add one person as a collaborator (settings -> Manage Access). Make sure everyone in the group has a collaborator.
- Create an issue in the repo where you are a collaborator
- Clone that repo
- make changes on a new branch
- push the changes
- submit a Pull Request
- wait for approval
- At the same time review a collaborators Pull Request
- (Optionally) Learn about [protecting branches](https://docs.github.com/en/github/administering-a-repository/about-protected-branches) and try it out.

#### Exercise: Working as an external contributor

- Remove your group member(s) as collaborators from your repository
- Fork another group members repo (Repository page, top right corner)
- Create an issue on the original repository
- Clone your forked repo to your computer
- Make some changes, use a somewhat real-world example so it makes sense to review it (but don't overdo it).
- Push it to your fork
- Make a change and commit it to the main branch
- push the changes
- make a pull request from your fork to the main repository mentioning the issue
- Consider turning your Pull Request into a draft Pull Request.
- let your code be reviewed by tagging the repo owner using (@Username)
- At the same time review Pull Request using comments on individual lines. Try to act as if it was a real peer review as much as possible.
- Accept or reject the Pull Request
- (Optionally) learn about [merge conflicts](https://www.atlassian.com/git/tutorials/using-branches/merge-conflicts) and try it out in your collaboration.

#### Recap + activation exercise:

**1 Think about what you learned:**
- What questions do you still have? 
- Whether there are any incremental improvements that can benefit your projects, 
- What’s nice that we learnt but is overkill for your current work? 


* Aafke:No questions at the moment. I think what we learned today was very useful, so no overkill of information. 
* Tareq: How is "fetch" used? - very useful day thank you. 
* Banafsheh:No question. A productive day!
* Nele: It was very useful. Since I myself usually work from the command line, it would be nice to get some resources on how to do some of these things (e.g. merge conflicts) also from the command line..................
* Wietske: No questions right now, today was very usefull and clear, in the future if I will collaborate I will use what I learned.
* Judith: I am still wondering if branches and forks would also be useful if your not collaborating? For example i ks would also be useful if your not collaborating? For example i ks would also be useful if your not collaborating?
* Michael: Today was very useful, but one question is that I still don't know how to deal with merge issues when I'm pushing from the command line. 
* Farzam: are there any best practices for the issue->branch->pull process? :+2:
* Antonio: Maybe one question: why is it called 'pull request' if what you want is to merge with an external repo? Otherwise everything was very well explained
* Nada:
* Akshatha: Can you use 'rebase commit' between the fork and the main repository?
* Paul: Is it good practice to use the terminal and the UI of Github or should you rather try to do everything with one only?
    * I think most frequent git users indeed use both. When developing I use the terminal, basically: develop, commit, develop, commit, push. For discussions, reviewing, merging etc. I use github web interface.
* Marieke:
* Justin:,
* Eef: Solving merge conflict is still unclear to me. Followed the small tutorial but here they only use command line tools which do not seem very useful when having large pieces of code?  
* Omar:
* Siri: So far everything was interesting
* Felicia: I often work within organizations on GitHub, are there any specific things I need to keep in mind?  :+1:
* Anne Fleur:
* Benito:
* Dario:
* Nicolas: Very useful workshop! I'll probably still run into problems when using the terminal for merging conflicts from time to time but don't have a concrete question now.
* Rodrigo:
* Kenzie:
* Shan: No further questions right now. Very good course, I will use it in the real world and learn more along the road.
* Bouke: No questions, think I should work, think I should work, think I should work, think I should work, think I should work, think I should work, think I should work, think I should work, think I should work, think I should work, think I should work, think I should work, think I should work, think I should work, think I should work, think I should work, think I should work, think I should work, think I should work
* Jeppe:
* Sandra: Need to learn more about forks, feature branches, and keeping them all in sync (real co-development with multiple people). Merge conflicts. Dealing with forks and branches on the command line. 
* Mark: How do you deal with if you fork X, make some changes to it locally, but in the meantime X has changed already? How do you push/pull/merge request? 
    * You can fetch and merge the changes of the original repository (the one you forked from) back to your own fork. There are some resources that you can find below.
* Mark: If you have multiple collaborators, do they all have 'super' access? I.e., can every collaborator accept merge requests. Is this good practice?
    * No, you can give different roles to different collaborators with different permissions. This is all very customizable. 
* Martine: No questions. Nice workshop
* Bram:
* Dirk-Jan: No questions, but showing the examples (branching and merging branches) on the commandline as well would be nice.
* Benito: Learned about how to work with forks and keeping them synchronized with the upstream. Also the reviewing part.

**2 What do you know about Continuous Integration?**

* Aafke: Nothing
* Tareq: Completely new to me. 
* Banafsheh: I am totally new to Continuous Integration
* Nele: The term does not ring a bell right now. I am not sure if I know about the concept without being aware of the term.
* Wietske: not much, my guess is that it makes sure that if you add a new part of code, all the old code still works?
* Judith: Never heard of it before
* Michael: Not much
* Farzam:
* Antonio: Not much. I guess it's a way to manage the git features we discussed today, but in a large team with many contributors working simultaneously
* Nada:
* Akshatha:Nothing
* Paul: Not much
* Marieke:
* Justin:
* Eef: Nothing really
* Omar:
* Siri: I am new to the concept
* Felicia:
* Anne Fleur:
* Benito:
* Dario: I have some basic idea of it and I collaborate in some projects that use Continuous Integration, but I am not able to implement it by myself.
* Nicolas: No idea
* Rodrigo:
* Kenzie:
* Shan:
* Bouke:
* Jeppe:
* Sandra: just know the concept; no practical expierience. 
* Mark: I don't even know what it means.
* Martine: As far as I understand: it is a automatic testbank to check that new code can be mergerd savely into main. Don't know how to use it in practice, though
* Bram:
* Dirk-Jan: First heard it here
* Benito: quite new to me too.

### What went well

* Aafke: It was very useful to have a lot of time to practice. 
* Tareq: Enjoyed working in a small group (breakout rooms)
* Banafsheh: The practice was so useful.
* Nele: The support during the breakout rooms was nice. Also good that there were additional tasks we could work on (e.g. protecting branches). 
* Wietske: Breakout rooms were very nice, content was clear! Also liked that there were enough breaks, feels really relaxed this way.
* Judith:
* Michael: Breakout rooms worked really well.
* Farzam: The structure and the material went well. Also enough time to do everything yourself with the help of the instrcutors 
* Antonio: The way contributions work from the two ends (project owner and collaborator) in life was nice
* Nada:
* Akshatha:
* Paul: The breakout rooms for the exercises went well imo. It was nice that the instructors stopped by once in a while
* Marieke:
* Justin:
* Eef:The presentations were clear. Communication in our breakout room went good.
* Omar:
* Siri:
* Felicia:Clear instructions, good breakout rooms.
* Anne Fleur:
* Benito: Breakout rooms worked really nicely, also good scheduled of the things to see.
* Dario:
* Nicolas: The breakout rooms worked well
* Rodrigo:
* Kenzie:
* Shan:
* Bouke:                                  
* Jeppe:
* Sandra: explanation was clear; practical examples were nice, although they don't seem to resemble real life yet. 
* Mark: I liked the interactive setup! Working in a small group was nice. 
* Martine: I liked the setup, it was really interactive. 
* Bram:
* Dirk-Jan:

### What could be improved

* Aafke: Maybe more helpers in the break out rooms
* Tareq: Can't really think of anything. Had an efficient and helpful morning!
* Banafsheh: I lost connection for a while and I missed a part. That would be nice to give a summary of each part at the end of each part, then we can catch up.
* Nele:
* Wietske:
* Judith:
* Michael:
* Farzam: not sure this can be fixed due to the different knowledge level of participants, but some exercises can feel too simple, or are dedicated too much time :+1:
* Antonio: I would have added a presentation on how to deal with conflicts. Also, I think some people got stuck in creating / linking the repos during the exercises. I would suggest to tell the students to do as preparation before the course. 
* Nada:
* Akshatha:
* Paul: Can't think of anything rn
* Marieke:
* Justin:
* Eef:
* Omar:
* Siri:
* Felicia: Some clearer instructions on the schedule/time plan so we know when to return from the breakout rooms and when to have breaks.
* Anne Fleur:
* Benito: A clearer explanation on the fetching from upstream repositories (from terminal/website) once you have done a fork and the original repository has been updated.
* Dario:
* Nicolas: Took me a while to find the extra materialook me a while to find the extra materialook me a while to find the extra material
* Rodrigo:
* Kenzie:
* Shan:
* Bouke:
* Jeppe:
* Sandra: add exercise with two parallel branches with (potentially conflicting) commits. Could even be a role playing game, mimicking a software company (or big research project), although this may be too extensive for a morning. 
* Mark: Could you let us know in advance if we are going to use breakout rooms? I expected today to be the same as yesterday (i.e., not much talking from my end) so I went to the office. However, some of my colleagues looked at me mad since I was talking from time to time ;-) 
* Martine: No tips really. Thanks and see you tomorrow
* Bram:
* Dirk-Jan:


### Commands + Glossary

* [General GitHub Documentation](https://docs.github.com/en/github)
* [GitHub Issues](https://guides.github.com/features/issues/)
* [Pull Requests](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/about-pull-requests)
* [Linking Pull Requests and Issues](https://docs.github.com/en/github/managing-your-work-on-github/linking-a-pull-request-to-an-issue)
* [Syncing Forks](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/syncing-a-fork)
* [GitHub Code Review](https://github.com/features/code-review/)
* [GitHub Workflow](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/github-flow)
* [Understanding the GitHub Workflow](https://guides.github.com/introduction/flow/)

### Questions

* Q:
    * A:

## 📚 Resources 

* [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
* [Connecting to github with ssh](https://docs.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh)
 