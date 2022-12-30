# Pulling changes from forked repositories

## The situation 
Imagine this—you are working on a feature in an open–source GitHub repo with a few others. You don't have write access, so you will need to make forks. If everyone is comfortable, one person can make a fork and give everyone else write access, but that's not always the case. 

## The solution
Each dev can make their own fork, and pull the others' changes as needed.

### Setting up a remote
Your teammate just pushed some changes, how can you pull them into your own repo?

First we need to set up a `remote`, which is short for "remote repository." 
```git
$ git remote add 
```