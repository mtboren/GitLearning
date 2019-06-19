## Git things ##

### Version control
Provides the ability to version files, code in collaboration with others, create a history with log entries, sync changes to a central repository, and share with the world

### Walkthroughs and interactive, online tutorials worth a grain
| Where | What |
|-------|------|
[https://git-scm.com/docs/gittutorial](https://git-scm.com/docs/gittutorial) | "A tutorial introduction to Git", from _the_ source
[https://learngitbranching.js.org/](https://learngitbranching.js.org/) | Learn Git, with eventual focus on branching

### Some very basics
  * Git has three main states that your files can reside in: committed, modified, and staged ([reference](http://git-scm.com/book/en/v2/Getting-Started-Git-Basics))
	  * Committed means that the data is safely stored in your local database (in the .git directory)
	  * Modified means that you have changed the file but have not committed it to your database yet (changed in working directory)
	  * Staged means that you have marked a modified file in its current version to go into your next commit snapshot
  * The basic Git workflow goes something like this: ([reference](http://git-scm.com/book/en/v2/Getting-Started-Git-Basics)) ([nice graphic](http://git-scm.com/book/en/v2/book/01-introduction/images/areas.png)) ([graphic of Git operations](http://ddayinc.com/tmp/git-operations.png))
	  * You modify files in your working directory
	  * `add`:  You stage the files, adding snapshots of them to your staging area
	  * `commit`:  You do a commit, which takes the files as they are in the staging area and stores that snapshot permanently to your Git directory
	  * `push`:  You push your updated local repository to some remote repository so that the world can be a better place (and so that your changes are not just local)


### Terminology

| Term | Definition |
|------|------------|
**repository** (.git directory) | where Git stores the metadata and object database for your project. This is the most important part of Git, and it is what is copied when you clone a repository from another computer
**working directory/tree** | a single checkout of one version of the project. These files are pulled out of the compressed database in the Git directory and placed on disk for you to use or modify
**staging area** or **index** | a file, generally contained in your Git directory, that stores information about what will go into your next commit. It’s sometimes referred to as the "index", but it’s also common to refer to it as the staging area
[**init**](http://git-scm.com/docs/git-init) | create an empty Git repository - basically a .git directory with subdirectories for objects, refs/heads, refs/tags, and template files. An initial HEAD file that references the HEAD of the master branch is also created
[**diff**](http://git-scm.com/docs/git-diff) | show changes between between two (or more) somethings -- two files, two file versions, two commits, files in the working directory and those in a commit, etc
[**add**](http://git-scm.com/docs/git-add) | update the staging area ("index") using the current content found in the working tree, to prepare the content staged for the next commit
[**status**](http://git-scm.com/docs/git-status) | show the working tree state 
[**commit**](http://git-scm.com/docs/git-commit) | store in the repository the current contents of the staging area ("index") in a new commit along with a log message from the user describing the changes
[**remote**](http://git-scm.com/docs/git-remote) | remote repositories ("remotes") whose branches the local repo is configured to track
[**push**](http://git-scm.com/docs/git-push) | update remote refs (repos) using local refs, while sending objects necessary to complete the given refs
[**log**](http://git-scm.com/docs/git-log) | show commit logs
[**pull**](http://git-scm.com/docs/git-pull) | incorporate changes from a remote repository into the current branch -- a fetch and a merge
[**branch**](http://git-scm.com/docs/git-branch) | the new line of development that results from diverging from the main line of development and continuing to do work without changing with that main line; see [Git Branching](http://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell) chapter for info
[**tag**](http://git-scm.com/docs/git-tag) | label specific points in history as being important. Typically people use this functionality to mark release points; see [Git Basics - Tagging](http://git-scm.com/book/en/v2/Git-Basics-Tagging) chapter for info
[**checkout**](http://git-scm.com/docs/git-checkout) | update files in the working tree to match the version in the staging area / index or the specified tree
[**clone**](http://git-scm.com/docs/git-clone) | copy a repository into a newly created directory, create remote-tracking branches for each branch in the cloned repository (visible using git branch -r), and create and check out an initial branch that is forked from the cloned repository’s currently active branch
**fork** | A fork is a copy of a repository. Forking a repository allows you to freely experiment with changes without affecting the original project. Most commonly, forks are used to either propose changes to someone else's project or to use someone else's project as a starting point for your own idea. More info at [GitHub fork help](https://help.github.com/articles/fork-a-repo/)


### Some example actions (work in progress):

0. config user name and email address for Git:

	`git config --global user.name 'Your Name'`

	`git config --global user.email 'your@emailaddr.com'`
0. create a repo
0. `clone` a repo
0. make changes
0. `add` changes
0. `commit` changes
0. `push` changes
0. `pull` changes in other working directory
0. create branch
0. change, add, commit, push
0. `merge` branch
0. inspect repo log in SourceTree


### Tools to sample:

* KDiff3 differencing tool, [http://sourceforge.net/projects/kdiff3/files/kdiff3/](http://sourceforge.net/projects/kdiff3/files/kdiff3/)
* SourceTree source/repo management and visualization, [https://www.sourcetreeapp.com/](https://www.sourcetreeapp.com/)

### Git resources:

* the Pro Git book, [http://git-scm.com/book/en/v2](http://git-scm.com/book/en/v2)
* Git reference, [http://git-scm.com/docs](http://git-scm.com/docs)
* posh-git, a PSModule for improved Git/PowerShell experience [https://github.com/dahlbyk/posh-git/releases](https://github.com/dahlbyk/posh-git/releases)

### Other helpful links:

* MarkDown syntax reference, [http://daringfireball.net/projects/markdown/syntax](http://daringfireball.net/projects/markdown/syntax)
* Visual Studio Code, an open, free, robust editor that includes (among many things) Markdown editing/rendering [https://code.visualstudio.com/](https://code.visualstudio.com/)
* [dillinger.io](http://dillinger.io/), an online MarkDown editor/renderer; consider your data privacy before using this online editor (not sure of how the data is retained at that site)
* "[A successful Git branching model](http://nvie.com/posts/a-successful-git-branching-model/)" by Vincent Driessen, a good post on one Git branching strategy that works
