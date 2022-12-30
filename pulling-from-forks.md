# Pulling changes from forked repositories

## Why use multiple forks? 
Imagine this—you are working on a feature in an open–source GitHub repo with a few others. You don't have write access, so you will need to make forks. If everyone is comfortable, one person can make a fork and give everyone else write access, but that's not always the easy to coordinate. 

### Setting up a remote
Your teammate just pushed some changes, how can you pull them into your own fork?

First we need to set up a remote repository, or for short, a remote. This will allow you to interact with other repositories—in this case, your teammates'. 

#### Checking remotes
If you are unsure which remotes you've already added, you can always check with this command

```
$ git remote -v
origin	https://github.com/<username>/<repo-name> (fetch)
origin	https://github.com/<username>/<repo-name> (push)
```

```git
$ git remote add 
```