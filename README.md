# Pushing a local repository to GitHub
## Create the local repository folder

We name it *demo_repo_local,* navigate to its folder then run: `git init` to initialise a repository

```bash
Initialized empty Git repository in C:/Users/lenovo/Desktop/Projects/Learn_git/demo_repo_local/.git/
```
## Add files 

Create the files you want and then run `git add .`

Check if the files are tracked by `git status`
```bash
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   README.md
```
## Commit changes 

Commit the changes by: git commit -m “*a message*”:
```bash
PS C:\Users\lenovo\Desktop\Projects\Learn_git\demo_repo_local> git commit -m "Created a README file"
[master (root-commit) 0bfd212] Created a README file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 README.md
```
if we tried now to push the code by `git push origin main` we will get an error:

```bash
error: src refspec main does not match any
error: failed to push some refs to 'origin'
```

And that is because the repo is created locally and in GitHub, while previously we cloned the repo from GitHub so we could push to GitHub directly.

## Make and connect to an empty GitHub repo
Now, to establish connection between our local repo and GitHub we need to create a new empty repo in GitHub

![image](https://github.com/user-attachments/assets/eec5f160-d771-4808-9afa-f42b25a093f7)

After that, copy the SSH link and back to the local repo terminal run the command: `git remote add origin SSH-link`

To check the remote repositories connected to our local repo run: `git remote -v`

```bash
PS C:\Users\lenovo\Desktop\Projects\Learn_git\demo_repo_local> git remote -v
origin  git@github.com:ILyass-Lr/demo_repo_local.git (fetch)
origin  git@github.com:ILyass-Lr/demo_repo_local.git (push)
```

## Push the changes
You can add the `-u` flag to specifies the default upstream to use so next time we can enter only `git push` and it well default to `origin master`:

```bash
PS C:\Users\lenovo\Desktop\Projects\Learn_git\demo_repo_local> git push -u origin master
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 229 bytes | 229.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:ILyass-Lr/demo_repo_local.git
 * [new branch]      master -> master
branch 'master' set up to track 'origin/master'.
```

