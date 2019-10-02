# A03

Step 1: Install git and create a GitHub account 
The first two things you'll want to do are install git and create a free GitHub account.

Note that for this tutorial we will be using git on the command line only. While there are some great git GUIs (graphical user interfaces), I think it's easier to learn git using git-specific commands first and then to try out a git GUI once you're more comfortable with the command. 

Once you've done that, create a GitHub account here.  (Accounts are free for public repositories, but there's a charge for private repositories.)

 
Step 1: Create a local git repository 
When creating a new project on your local machine using git, you'll first create a new repository (or often, 'repo', for short). 

To use git we'll be using the terminal. If you don't have much experience with the terminal and basic commands, check out this tutorial (especially the 'Navigating the Filesystem' and 'Moving Around' sections).

To begin, open up a terminal and move to where you want to place the project on your local machine using the cd (change directory) command.

To initialize a git repository in the root of the folder, run the git init command

Step 2: Add a new file to the repo
Go ahead and add a new file to the project, using any text editor you like or running a touch command.

Once you've added or modified files in a folder containing a git repo, git will notice that changes have been made inside the repo. But, git won't officially keep track of the file (that is, put it in a commit - we'll talk more about commits next) unless you explicitly tell it to.

After creating the new file, you can use the git status command to see which files git knows exist.

(use "git add <file>..." to include in what will be committed)
 

An interlude: The staging environment, the commit, and you
One of the most confusing parts when you're first learning git is the concept of the staging environment and how it relates to a commit.

A commit is a record of what files you have changed since the last time you made a commit. Essentially, you make changes to your repo (for example, adding a file or modifying one) and then tell git to put those files into a commit.

Commits make up the essence of your project and allow you to go back to the state of a project at any point.

So, how do you tell git which files to put into a commit? This is where the staging environment or index come in. As seen in Step 2, when you make changes to your repo, git notices that a file has changed but won't do anything with it (like adding it in a commit).

To add a file to a commit, you first need to add it to the staging environment. To do this, you can use the git add <filename> command 
  
Once you've used the git add command to add all the files you want to the staging environment, you can then tell git to package them into a commit using the git commit command. 


Step 3: Add a file to the staging environment
Add a file to the staging environment using the git add command. 

If you rerun the git status command, you'll see that git has added the file to the staging environment (notice the "Changes to be committed" line).  


To reiterate, the file has not yet been added to a commit, but it's about to be.

 

Step 4: Create a commit
It's time to create your first commit!

Run the command git commit -m "Your message about the commit"

The message at the end of the commit should be something related to what the commit contains - maybe it's a new feature, maybe it's a bug fix, maybe it's just fixing a typo. Don't put a message like "asdfadsf" or "foobar". That makes the other people who see your commit sad. Very, very, sad.

 

Step 5: Create a new branch
Now that you've made a new commit, let's try something a little more advanced.

Say you want to make a new feature but are worried about making changes to the main project while developing the feature. This is where git branches come in. 

Branches allow you to move back and forth between 'states' of a project. For instance, if you want to add a new page to your website you can create a new branch just for that page without affecting the main part of the project. Once you're done with the page, you can merge your changes from your branch into the master branch. When you create a new branch, Git keeps track of which commit your branch 'branched' off of, so it knows the history behind all the files. 

Here's what you'll do: Run git checkout -b <my branch name>. This command will automatically create a new branch and then 'check you out' on it, meaning git will move you to that branch, off of the master branch.

Now, if you switch back to the master branch and make some more commits, your new branch won't see any of those changes until you merge those changes onto your new branch.

 
Step 6: Create a new repository on GitHub
If you only want to keep track of your code locally, you don't need to use GitHub. But if you want to work with a team, you can use GitHub to collaboratively modify the project's code.

To create a new repo on GitHub, log in and go to the GitHub home page. You should see a green '+ New repository' button: 

After clicking the button, GitHub will ask you to name your repo and provide a brief description:


When you're done filling out the information, press the 'Create repository' button to make your new repo.
 

Step 7: Push a branch to GitHub
Now we'll push the commit in your branch to your new GitHub repo. This allows other people to see the changes you've made. If they're approved by the repository's owner, the changes can then be merged into the master branch.

To push changes onto a new branch on GitHub, you'll want to run git push origin yourbranchname. GitHub will automatically create the branch for you on the remote repository

Origin happens when you clone a remote repository to your local machine, git creates an alias for you. In nearly all cases this alias is called "origin." It's essentially shorthand for the remote repository's URL. So, to push your changes to the remote repository, you could've used either the command: git push git@github.com:git/git.git yourbranchname or git push origin yourbranchname

If you refresh the GitHub page, you'll see note saying a branch with your name has just been pushed into the repository. You can also click the 'branches' link to see your branch listed there.
 

Step 8: Create a Pull Request
A pull request (or PR) is a way to alert a repo's owners that you want to make some changes to their code. It allows them to review the code and make sure it looks good before putting your changes on the master branch.

You might see a big green button at the bottom that says 'Merge pull request'. Clicking this means you'll merge your changes into the master branch.

Note that this button won't always be green. In some cases it'll be grey, which means you're faced with a merge conflict. This is when there is a change in one file that conflicts with a change in another file and git can't figure out which version to use. You'll have to manually go in and tell git which version to use.

Sometimes you'll be a co-owner or the sole owner of a repo, in which case you may not need to create a PR to merge your changes. However, it's still a good idea to make one so you can keep a more complete history of your updates and to make sure you always create a new branch when making changes.

Step 9: Merge a PR
Go ahead and click the green 'Merge pull request' button. This will merge your changes into the master branch.
 

Step 10: Get changes on GitHub back to your computer
Right now, the repo on GitHub looks a little different than what you have on your local machine. For example, the commit you made in your branch and merged into the master branch doesn't exist in the master branch on your local machine.

This shows you all the files that have changed and how they've changed.

Now we can use the git log command again to see all new commits.

(You may need to switch branches back to the master branch. You can do that using the git checkout master command.)
