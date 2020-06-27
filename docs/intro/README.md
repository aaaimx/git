# Respositorios locales

## Configuración inicial

Configure la información del usuario para todos los repositorios locales

- Establece el correo electrónico que desea adjuntar a sus transacciones de confirmación

      $ git config --global user.email "[email address]"

- Establece el nombre que desea adjuntar a sus transacciones de confirmación

      $ git config --global user.name "[name]"

## Create repositories

When starting out with a new repository, you only need to do it
once; either locally, then push to GitHub, or by cloning an
existing repository.

\$ git init
Turn an existing directory into a git repository

\$ git clone [url]
Clone (download) a repository that already exists on
GitHub, including all of the files, branches, and commits


## Make changes
Browse and inspect the evolution of project files

$ git status
Outputs metadata and content changes of the specified commit

$ git add [file]
Snapshots the file in preparation for versioning

\$ git commit -m "[descriptive message]"
Records file snapshots permanently in version history

$ git log
Lists version history for the current branch

## The .gitgnore file

Sometimes it may be a good idea to exclude files from being
tracked with Git. This is typically done in a special file named
.gitignore . You can find helpful templates for .gitignore
files at github.com/github/gitignore.

## The .gitkeep file


## Branches

Branches are an important part of working with Git. Any
commits you make will be made on the branch you're currently
“checked out” to. Use git status to see which branch that is.
\$ git branch [branch-name]
Creates a new branch

\$ git checkout [branch-name]
Switches to the specified branch and updates the
working directory
