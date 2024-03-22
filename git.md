# Git Snapshot | Steps | Workflow — 1
While many people perceive Git as a confusing and complicated tool, it's actually quite simple once you become more familiar with it. Like many other areas of knowledge, all it takes is getting accustomed to it. Trust me, it's not as tangled as quantum physics.

---

#Steps to create snapshot
In order to snapshotting a working directory, there are some basic commands.
`$ git status
$ git add
$ git commit`

These tree commands represent two basic steps for capturing a snapshot of your working directory. While the 'status' command is merely informational, it's still beneficial to understand what it reveals about your actions :)
lets imagine we created a repository in our local system and now we are going to add a file into them.
first we check the status of our local repository by using 'status' commad:

```bash
git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
 example.txt

nothing added to commit but untracked files present (use "git add" to track)
```
As we can see, there is nothing on our stage, and the file 'example.txt' is under the 'Untracked files' category. This generally indicates that Git doesn't care about that file until we add it to the stage and create a new snapshot. After that, Git will monitor all files that have taken at least one snapshot.
The 'add' command is used to stage files, thereby indicating Git's awareness of them.

```bash
git add example.txt
```
Let's check the status of our repository again to see what has changed.

```bash
git status

On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
 new file:   example.txt
```
At this point, Git is actively tracking the file and is prepared to capture a snapshot of it, or in other words, the file is ready to be committed.
lest see this workflow in a diagram.

![Add to stage](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/nu4384w97xlocjh3skni.png)

For our final action, we are going to create a commit message, and Git will take a snapshot of the current state of the repository.
The '-m' flag allows us to use an inline commit message. Without it, Git will open the system's default editor(vscode, nano, vim, etc…).

```shell
git commit -m "this is init commit"

[master (root-commit) ed942fe] this is init commit
1 file changed, 0 insertions(+), 0 deletions(-)
create mode 100644 example.txt
```
Congratulations, you've done it! 
That's precisely what's needed to keep track of changes to our files. 
In return, Git provides a report of what was committed. I'll discuss the details of this report in a separate document. However, generally, this report informs us that we committed on the master branch, and the SHA-1 checksum is 'ed942fe'. We can use this checksum to 'check-out' between our snapshots. In other words, this checksum is the signature of our snapshot, allowing Git to locate your target snapshot.

![Commit changes](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/lgobnpbr3i7hevjamcvc.png)

---
## In conclusion
Git stands as one of the most prominent tools in the software world, particularly among programmers. Throughout this process, we've acquired the knowledge of adding new files to the staging area and committing changes, laying the groundwork for effective version control and collaboration in our software projects.
