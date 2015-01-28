**WDI Fundamentals Chapter 2**

---

## Get Started with Git

Git gets to work once you add a folder called ".git" into the folder you would like track. To add this special folder, you need to use the command line (see, told you that thing would be useful). 

###Initialize your First Repository

The folder that contains `.git/` is called a **repository** (or **repo** for short) and the process of adding `.git/` to an empty folder is called initializing a repository:

    $ git init

Running this command will create a new `.git/` directory, which will contain all the data for the history of your entire project. 

When you take a look at a repo in the GUI you might not see any additional files, because (if you remember from Unit 1) hidden files are not visible by default on your computer.  To see the `.git/` directory you need to run `ls -a` from command line, which lists all the files in your repo.


### Saving Versions of Your Project

Aptly named, Git is not too bright.  It needs you to tell it which files to track and how often to save a version of them.  

Now that you have initialized your repo, you can instruct Git to track all the contents of the repo. 

Then, every time you want to save a version, a snapshot of all the contents of that repo, you tell Git to **commit** that version to memory.

If you want to revert to an old version you can do that. If you want to view the difference between two versions of a file, you can do that too.

Let's take a look at an example.  

We would like to work on a blog post for General Assembly, so we created an empty repo on our desktop called "GA-Blog". The file structure looks like this:

```
GA-Blog
|____.git
| |____config
| |____description
| |____HEAD
| |____hooks
| | |____applypatch-msg.sample
| | |____commit-msg.sample
| | |____post-update.sample
| | |____pre-applypatch.sample
| | |____pre-commit.sample
| | |____pre-push.sample
| | |____pre-rebase.sample
| | |____prepare-commit-msg.sample
| | |____update.sample
| |____info
| | |____exclude
| |____objects
| | |____info
| | |____pack
| |____refs
| | |____heads
| | |____tags
```

This looks like a lot of content, but really there is only one folder in this GA-Blog repo: `.git/`.

To see what Git knows about this project, we would run:

```
$ git status
```

Now take a look at the computer's response:

![Git Status of GA-Blog](../assets/chapter2/git_status.gif)

There are no changes to the GA-Blog folder for Git to remember or "commit".

Let's go ahead and make a new text file called "post.txt" inside of GA-Blog, using the `touch` command.

Now let's check our Git status:

![Git Status of GA-Blog](../assets/chapter2/git_status_untracked.gif)

Git has identified that there is new a file in our repo, but it does not know whether or not we want it tracked.

We want to add the file we made to the GA-Blog repo to our next commit.  To do this we run:

```
$ git add post.txt
```

If we now run `git status` we'll see that the file is ready to be committed:

![Git Status of GA-Blog](../assets/chapter2/git_status_staged.gif)

> **NOTE** Typically, you'll want to track all of the contents of your repo, so instead of specifying a unique file you should write `git add .` (remember `.` is shorthand for the working directory).

So this new version of our GA-Blog project is now in what's called the staging area.  Git is giving you a chance to change your mind before commiting. 

> **CAUTION** You must add files to the staging area before committing them.

We're ready to tell Git to record a snapshot of our project. Finally, we can type:

    $ git commit -m "message explaining what changes you made"

The `-m` option allows you to include a message, describing the changes you made for your collaborators or future-you. 

You should commit as often as possible to prevent making changes that you can't revert back to.


### The Git Staging Area




### Benefits of Git

When you're working with Git, you are working with your own copy –what we refer to as your "local" copy. With your local copy, you can do whatever you want. Add new fonts, change todo en español.

This is your local copy and you're not affecting others. You can commit changes to your local copy (even without Internet access) and decide to abandon it all and get a fresh copy from the remote.