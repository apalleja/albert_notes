# Git commands and Github

> Author: Albert Palleja Caro

Write something using markdown syntax. You can use the 
[Markdown Guide](https://www.markdownguide.org/basic-syntax/) or
[GitHub Docs Guide](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
to learn more about the markup syntax.

Here are some of my notes about Github and git system

From https://www.youtube.com/watch?v=RGOj5yH7evk

# **git commands**
> git clone # bring a remote repository in your local folder
> git add # let git know about file changes so taht it tracks them
> git commit # save these changes to git
> git push # save the changes in the remote repository like Github (could be bitbucket or other alternatives)
> git pull # download changes from a remote repository, oppositte to push


# From a folder to initialize git:

> git init
> git status
> git commit -m "Creat README.md" -m "description"

Then you have to creat the repo from Github. GO to Github, new repository then accept and copy the git address

Adding a reference to the remote repository git@github.com:/apalleja/repo.git
> git remote add origin git@github.com:/apalleja/repo.git
> git remote -v # all remote repositories connected to this repo
> git push -u origin main # the -u says that is where we want to push by default

/var/folders/q2/yzskpkwn0xz45r_s67cxw6qc0000gp/T/TemporaryItems/NSIRD_screencaptureui_EO3C9L/Screenshot 2024-10-01 at 11.00.03.png

# **git branching**
/var/folders/q2/yzskpkwn0xz45r_s67cxw6qc0000gp/T/TemporaryItems/NSIRD_screencaptureui_LzgtDu/Screenshot 2024-10-01 at 11.09.11.png
```
> git branch
> git checkout -b feature-readme-instructions # create a new branch called feature-readme_instructions
> git checkout main # I come back to main branch
> git checkout feature-readme-instructions # I come back to the feature branch
```

## Then we make changes and have to do
```
> git add
> git commit -m "Updated readme"
```

```	
> git diff feature-readme-instructions # all lines that have change between two codes
> git push -u origin feature-readme-instructions
```

# **Make a pull request**: your code pulled in another branch PR from feature --> main. You collabs can review the code / comments, etc... 
# In Github you can compare and pull request, there you can add some comments and pull request. You can then check all changes, make comments to those, resolve them and the Merge Pull request

# to get the changes from the remote main (Github) to your local repository:
```
> git checkout main # changing to the main branch
> git pull origin main # or only git pull (if you have already set your upstream)
> git branch -d feature-readme-instructions # deleting your feature branch no longer needed
```

# Conflicts with different branches
```
> git checkout -b quick-test1
> git commit -am "added world to hello" # with -am you can add and commit at the same time, only for already modified at least oncce files
> git checkout main
```

# You make changes in main then
```
> git checkout -b quick-test1
ERROR because you have not commited your last change
> git status
> git commit -am "Added there"
> git checkout quick-test1
> git diff
> git merge master # merging locally is not the regular pattern. However you do not want to get too far behind, to keep updated to the main changes in main
CONFLICT --> Easisest way to fix the conflicts fix them in VS Code. Change to check are between <<<< HEAD ... >>>> master You change in VS COde
> git status
> git diff
> git commit -am "updated with main"
# Then it is solved the conflict with main and I can continue doing what I was doing in th quich test1 branch 
```

# **Undoing git**
```
> git reset README.md # unstage the file README
> git reset HEAD~1 # unstaged and uncommitted the last change
> git log # to see all commits in reverse chronological order, scroll down with space bar
> git reset hash_of_the_commit # unstaged up to this commit 
> git reset --hard hash_of_the_commit # all changes not only unstaged but also completely removed
```

# Forking, is necessar when you want a complete copy of the code of someone else
# Fork it in Github to your personal github and pull it to your local folder. Make all changes you want on the code and 
# When you have done all changes that you wanted you can do a PR in the original repository if you plan to merge to code with the original
# SOme repositories have a main and a dev branch, some only allow the pull requests to the dev and later if approved they are merged to the main branch.


# Stash you can stash your changes for a while and bring them back at some other point

# to go changes chuncks separately 
```
git add -p file_changed
```
# then letters to decide what to do on each code chunk
