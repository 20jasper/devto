# Pulling changes from forked repositories

## Why use multiple forks? 
Imagine this—you are working on a feature in an open–source GitHub repo with a few others. You don't have write access, so you will need to make forks. If everyone is comfortable, one person can make a fork and give everyone else write access, but that's not always the easy to coordinate. 

### Remotes
Your teammate just pushed some changes, how can you pull them into your own fork?

First we need to set up a remote repository, or for short, a remote. This will allow you to interact with other repositories—in this case, your teammates'. 

#### Checking remotes
If you are unsure which remotes you've already added, you can always check with this command

```
$ git remote -v
origin	https://github.com/20jasper/git-tutorial (fetch)
origin	https://github.com/20jasper/git-tutorial (push)
```
Note that origin isn't a special keyword—it's just the default name for a repo's main remote
#### Adding new remotes
Typing out the whole url for a remote every time would be confusing, but luckily, each remote can be given a name just like `origin`. 

Let's say our teammate is called Jimothy, and to keep it simple, let's use `jimothy` for the name of the remote as well.

```git
$ git remote add jimothy https://github.com/jimothy/git-tutorial
```