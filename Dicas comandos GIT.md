# Git - Comandos úteis

## Como criar um repositório no Git via linha de comando

```git
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/rlucioda/documentation.git
git push -u origin master
```

* …or push an existing repository from the command line

```git
git remote add origin https://github.com/rlucioda/documentation.git
git push -u origin master
```

* …or import code from another repository

You can initialize this repository with code from a Subversion, Mercurial, or TFS project.

* HTTPS: <https://github.com/rlucioda/documentation.git>

* SSH: git@github.com:rlucioda/documentation.git#

### Logs

`git log --graph --decorate --abbrev-commit --pretty=oneline --all`

### Config Settings

`git config --global user.name "Ricardo Conceição"`

`git config --global user.email 'rlucioda@opentext.com'``

### Config Settings


## How to checkout a remote branch in git?

![alt](https://www.educative.io/api/edpresso/shot/4793369437929472/image/6586281372942336https://link)

**1. Fetching all remote branches**

First, fetch all the remote branches from the repository. Assuming that your remote name is origin, you can do it like this:

```git
git remote

# origin

git fetch origin

```

**2. Check branches available for checkout**

Then you can check all the branches that are available for checkout, like this:

`git branch -a`

The output of this command will be all the branches available in the local repository, along with all the branches fetched from the remote. The branches fetched from the remote **origin** would be preceded by **remotes/origin/**.

**3. Making a local copy of the branch**

You cannot make changes in somebody else’s branch. In order to work on someone’s branch, you would have to make a local copy of it, which can then be pushed to the remote host:

`git checkout -b <name-your-branch> origin/<name-of-remote-branch>`

After this, you can start working on your copy of the fetched remote branch!

Referência [edpresso](https://www.educative.io/edpresso/how-to-checkout-a-remote-branch-in-git?affiliate_id=5082902844932096&utm_source=google&utm_medium=cpc&utm_campaign=platform2&utm_content=ad-1-dynamic&gclid=Cj0KCQjwjOrtBRCcARIsAEq4rW4TJcJMsGTxO7n7OSJ6d4_KhjP-Y4rOFnEpNNHIrsjiID4zwPuSuD0aAoVEEALw_wcB)

## Outras referências 

[What are some important git commands?](https://www.educative.io/edpresso/what-are-some-important-git-commands)

[How to squash commits in Git - rebase](https://www.educative.io/edpresso/how-to-squash-commits-in-git)
