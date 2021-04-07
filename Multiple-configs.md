# How to use Multiple Git configs

The idea is to segregate repos that use different git configs.

## Step 1: Create separate directories for different configs

Organize the projects that you work into separate repos.

For example, all the work related repos could be under a dir called `WORK` and personal projects under `PERSONAL`.

## Step 2: Add these repos in global git config

Access the global git config which looks like this `.gitconfig`.

It's usually under home directory and you can use this `ls -a ~ | grep .git` command to list if there any files that start with `.git`.

Add the below lines of code in the global `.gitconfig` file.

```bash
[includeIf "gitdir:~/PERSONAL/"]
  path = ~/.gitconfig-personal
[includeIf "gitdir:~/WORK/"]
  path = ~/.gitconfig-work
```

```text
What we are telling here, is that the git config for the dir in path `~/PERSONAL/` is `~/.gitconfig-personal` and the git config for the dir `~/WORK/` is `~/.gitconfig-work`
```

## Step 3: Create configs for each repo

As aforementioned in the global `.gitconfig` we need to create two config files:

- .gitconfig-personal
- .gitconfig-work

and they have to be present in the home path i.e., `~`

### .gitconfig-personal

You can have the customizations you need in the config:

```
[user]
 name = personal_user
 email = personal_email
```
### .gitconfig-work

```
[user]
 name = work_user
 email = work_email 
```

## Step 4: To test the config

Goto the directory PERSONAL and you can initilize a new git directory under that.

`cd ~/PERSONAL && mkdir demo && cd demo && git init`

The above command, navigates you to `PERSONAL` repo and creates a new dir called `"demo"` and initializes git in that repo.

You can check the git config in that repo by using the command `git config -l`

This should list you the config that you have provided under `.gitconfig-personal`.

And that's it! You have successfully created multiple configs and asssigned repos that uses them.

