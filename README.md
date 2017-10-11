# git-tutorial
Workshop material for StartupStorm's Git tutorial  
If you see any type / improvements, feel free to send us a PR

![Git Logo](https://git-for-windows.github.io/img/git_logo.png)

## Instructions
### Step 0. Terminology
Through out this workshop, we'll be using a set of new terminology.
- **Repo** is a project folder hosted on GitHub
- **Fork** is an act of copying the project. This ia a recommended approach to make a pull request.
- **Pull Request (PR)** is sending the code edit you made to the project you intend to contribute to.
- **Pushing** your code is to push your local file change to GitHub
- **Pulling** code is to get the latest version of files from a GitHub repo


These terms will be explained as we go

### Step 1. Set up
First, make an account at [GitHub](https://github.com/join)

Install git on your system following one of these guides:
- [OS X](https://www.atlassian.com/git/tutorials/install-git#mac-os-x)
- [Windows](https://www.atlassian.com/git/tutorials/install-git#windows)
- [Linux](https://www.atlassian.com/git/tutorials/install-git#linux)

We will be editing text file in this workshop, so use whatever program you're most confortable with (Sublime, Atom, Default text editor, etc)

Lastly, run these initial set up commands on your terminal

```
// Set name shown under your git commit
$ git config --global user.name "User Name"

// Set email shown under your git commit
$ git config --global user.email "email"
```

And you're ready to start using Git!

### Step 2. Fork and clone
Next step is to [fork](https://help.github.com/articles/fork-a-repo/) this repo!

1. Fork the repo
Click on the top right button on this page that's saying "Fork".  
After a moment of cloning, you will be jumped to the newly clone repo within your account.
At this poing the URL of the page should be `https://github.com/YOUR_USER_NAME/git-tutorial`

2. Clone the repo
Click on "Clone or download" green button on your clone git-tutorial repo
![This green button](https://imgur.com/vK3c3Lu)
Copy the link!

Go to your terminal and type in the following at the location you want to copy the project

```
$ git clone https://github.com/YOUR_USER_NAME/git-tutorial
```

Conglatulations :tada: you just copied the project to your computer!

### Step 3. First contribution
Make your own branch, and switch to it

```
$ git branch add-YOUR_NAME
$ git checkout add-YOUR_NAME
```

Add your name to attendes.txt and save it  
At this point if you run 

```
$ git status
```

You should see `/attendees` directory / folder  
Create and add a new file in this directory following the instructions in `/attendees/guide.txt`

Let's commit the changes you've made. Run these command to add and comit the changes.

```
$ git add .
$ git commit -m "Add YOUR_NAME.txt file in /attendees"
$ git push origin add-YOUR_NAME
// Note: Push command specifes the branch name to push to with the last argument (in this case add-YOUR_NAME)
```

Now you've pushed your edit to GitHub!  
If you go to  https://github.com/YOUR_USER_NAME/git-tutorial, you should see the changes reflected on files :thumb-up:

### STEP 4. Make a PR

Now let's reflect the change on the original project's repo!
Once you visit https://github.com/YOUR_USER_NAME/git-tutorial, you should see a pop up suggesting you to make a PR

![Something like this](https://i.imgur.com/q3c3Ulq.png)

Click "Compare & pull request button", then click "Create pull request"

Afterward, you should see you pull request on the original project's PR list

![Your PR shown here](https://i.imgur.com/qb048Tn.png)

That's it! You just did the whole flow of doing open source :tada:  
Let one of the organizers know that you did this step, and we'll merge you PR right away.

### Step 5. PULLING + ADDING

Let's return to the master branch for a second

```
$ git checkout master
```

Wait until the organizer add a new file to the project.
Common thing that will happen is that some other people add a new file to the project.  
There should be a way to get the latest version of the project, and there is one.

Run this command

```
$ git remote add upstream https://github.com/startupstorm/git-tutorial
```

This command will create a new remote endpoint at our original project repo, named `ss`
To pull, you run

```
git pull upstream
```

You should now see new files in your computer!

## Challenge Problems
### Extra 1

As you go learn git, there will be many new commands you'll learn along the way.

One of them is `git log` command which shows you the past git commits of the branch.

If you run this command in the `master` branch, you will see a paragraph with "EXTRA 1"
There is a hidden instruction there for this problem.

Make a PR once you're done with the PR title `Extra 1 - YOUR_NAME`

### Extra 2
Continuing on with `git log`, another great feature is that it tells you who made a commit to the project.
Identify who introduced a bug to the project based on commit author name and commit message

### Extra 3
Another great command is `git commit --amend`  
This command let you edit the past commit message in case you made a typo or wanna change it.

To understand how it works, let's create a new branch
```
$ git checkout commit-ammend-YOUR_NAME
```

Inside your `./attendees/YOUR_NAME.txt`, add line to state which year + program you are in

Let's commit this in a normal manner

```
$ git add .
$ git commit -m "Add year + program"
```

After you made the commit, check the commit message shown in the log
```
$ git log
```

Now, let's say that this project required contributers to write commit messages in all caps.
Since the code change itself is okay but just the commit message, this is a great use case for amend

Run the following command
```
$ git commit --amend "ADD YEAR + PROGRAM"
```

Run log again to verify that the commit message has been updated.

Hooray! you know how to use Git now :tada:
