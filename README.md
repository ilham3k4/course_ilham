# course_ilham
repository for crash course 2022

Summary Git in depth

Summary of git in depth course by Nina Zakharenko.
The goal of this class is to understand and learn more about git. The concept, how it works, and the flow. For that, the course will use the command line to understand git better and not through application/wizard, since it created to spare you the trouble. however the command line will not be included in this summary for simplicity sake.

Data Storage :
Git stores the compressed data in a blob, along with meta data in the header. Git store its data in git directory which contains data about our repository, and the blobs are stored in git objects. In git object, the blob missing some information (filename, directory structures) which is stored in a tree. A tree contain pointers to blobs and other trees because directory can be nested.
Git commit point to a tree and contains meta data such as author and committer, date, message and parent commit. A commit is a code snapshot, what the project looks like at that point in time, a combination of changes from staging area of previous commit. We can’t change commits, if you change any data, the commits will have a new hash, even if the data dont change the created date will.

Git Areas and Stashing : 
Three areas where code lives : working area (or sometimes called as working tree), staging area (or cache or index) and repository. The working area are the files in your working area that are not in staging area and not handled by git, basically the files in your local directory in your computer. The staging area is how git knows what will change between the current commit and the next commit.
The repository contains all your commits.
Git stash is used to save un-committed work and safe from git destructive operation like changing branches while in the middle of work or overwriting file. And you can apply it back to your branch anytime when needed.

Reference, commits and branches :
Tags point to a commit but store additional information such as author, message and date.
Branch  point to a commit on the top of a development line and will change when a new commit is pushed whereas a tag will not change. Thus tags are more useful to "tag" a specific version and the tag will then always stay on that version and usually not be changed. detached HEAD occurs when you are viewing a single commit in the history of a Git repository. You'll see a message whenever you enter into detached HEAD state informing you that you are no longer on a branch.
Dangling commit is A commit that isn't directly linked to by any child commit, branch, tag or other reference and you can get it back in garbage collection.

Merging and rebasing :
Git merging combines sequences of commits into one unified history of commits. Git can automatically merge commits unless there are changes that conflict in both commit sequences.
Fast forward merge means to update the HEAD pointer in such a way that its new value is a direct descendant of the prior value. Merge conflicts happen when attempting to merge but the files diverged, git stops until the conflicts are resolved.
Git RERERE (Reuse Recorded Resolution) saves how you resolved the conflict and reuse the same solution for the next conflict which saves you a lot of time. Useful for long lived featured branch or rebasing.

History and diffs :
As project drags on, some git commits messages might get less and less informative and this is bad. Good commit help preserve the history of code base and it will help with a lot of thing such as debugging, code review or roll back data.
Git log is a basic command that shows you the history of your repository.
Diff show the changes between commits, staging area and repository, what’s in working area. It also can be used to check which branch are merged with master.

Fixing Mistakes : 
Git checkout restore working tree files or switch branches. It changes HEAD to point to new branch, copy the commit snapshot to the staging area, and update the working area with the new branch contents. Basically replace/overwrite the working area with the version from the current staging area.
Git clean will clear your working area by deleting untracked files and cannot be undone.
Git reset will move the current HEAD to the commit, meaning your branch is now modified and can change its history.
Git revert or known as “safe” reset to undo changes, it create a new commit from the specified commit and the original commit stays in the repository, and it does not change history.

Rebase and amend :
Amend is a quick and easy shortcuts that let you makes changes to the previous commit.  Rebase is Git utilities that specializes in integrating changes from one branch onto another. Rebase commits can be edited, removed, combined and inserted. The difference between merge dan rebase basically : Merge takes all the changes in one branch and merges them into another branch in one commit, while Rebase says I want the point at which I branched to move to a new starting point.
autosquash are helpful features when you want to “fix” changes from a single commit in your history. An interactive rebase with --autosquash option will then merge the original commit and the fixup into a new commit and rebase the subsequent commits.
abort will abort the merge process and try to reconstruct the pre-merge state.

Github vs git :
The key difference is collaboration. Git open source version control software. While GitHub is the key for collaborating with other developer, GitHub is a tool built on top of git with easy to use interface.
Remotes is a git repository that stored elsewhere, on the web, on the GitHub, on company private server etc. Origin is the default name git gives to the server you cloned from. Cloning a remote repository from url will fetch the whole repository and makes a local copy in your git folder.
Fork is a copy of repository that’s stored in your GitHub account, you can clone your fork to your local computer.
pull request is an event in Git where a contributor asks a maintainer of a Git repository to review code they want to merge into a project.
upstream allows you to set the default remote branch for your current local branch. By default, every pull command sets the master as your default remote branch.
triangle workflow involves an upstream project and a personal fork containing a development branch of the project.
Fetch pull down all changes that happen on the server, and it doesnt change your local repository.
Pull will pull down the changes from remote repository to your local repository and merging them with a local branch.
Push send your changes to the remote repository, git only allows you to push if the changes won’t cause conflict.

Thats all for the summary, I hope its sufficient enough. Thank you for reading!

