# Setup Git

After setting up a git account. create a different SSH Key.
Follow the steps [here](https://docs.github.com/en/github/getting-started-with-github/set-up-git) to set up a git account.

## Checking for existing SSH keys

To check for existing SSH keys:

1. Open Git Bash.

2. Enter `ls -la ~/.ssh` to see if existing SSH keys are present.

3. Check to see if directory has any public SSH keys. Default filenames of the public keys are like these:

- id_rsa.pub

## Creating an SSH Key

If you don't have any existing SSH keys, follow the steps [here](https://docs.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#generating-a-new-ssh-key).

## Add the keys

Use `ssh-add ~/.ssh/id_rsa_xxxx` to add the ssh keys.

To delete all the cached keys before

`ssh-add -D`

To list the existing keys, use

`ssh-add -l`

## Modifying the SSH Config

$ cd ~/.ssh/
$ touch config

## Update the hosts in the SSH config file

### My Company Github Account

Host github-mycompany.com
HostName github.com
User git
IdentityFile ~/.ssh/id_rsa_my_company

### Personal Github Account

Host github.com
HostName github.com
User git
IdentityFile ~/.ssh/id_rsa

## Clone your personal Github and company Github projects

You can clone your personal private projects using the command,

`git clone git@github.com:your-github-account/private-repo.git`

You can clone your company ‘s private projects using the command,

`git clone git@github-mycompany.com:company-acc/private.git`

That’s it. Hope it will be useful.
