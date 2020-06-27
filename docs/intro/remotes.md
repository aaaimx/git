# Repositorios remotos

## Agregando remotos

$ git remote add origin [url]

$ git remote set-url origin [url]

## Claves SSH

https://github.com/settings/keys

Configura tus claves SSH para Github [aqui](https://help.github.com/es/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account)


## Synchronize changes

Synchronize your local repository with the remote repository
on GitHub.com
$ git push
Uploads all local branch commits to GitHub
$ git merge
Combines remote tracking branch into current local branch
\$ git fetch
Downloads all history from the remote tracking branches

\$ git pull
Updates your current local working branch with all new
commits from the corresponding remote branch on GitHub.
git pull is a combination of git fetch and git merge

## Manejando versiones y tags

    $ git tag 1.0.0 [commit-id]
    $ git tag -a v2.2.0 -m "Primera version estable (Jun 17, 2020)"
    $ git tag -d v1.0.0