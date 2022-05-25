# FUTUREPROOF - Lap 2 - Week 1

Auguste Cohort - Exercise on docker-compose and git submodule.

## How to use two of your own repos by using git submodule

#### Create a new folder, cd into it and initialise a git repo

```bash
  mkdir docker-compose-exercise
  cd docker-compose-exercise
  git init
```

#### Use the following command replacing <repo> with your actual repos

```bash
  git submodule <repo> <folder-name>
```

This will clone the repo into a folder called <name> and will allow you to git push your main repo without interference from within the <repo> folder (Remember that git doesn't allow having .git folders within a repo's subfolders).

##### Example

- Repo to clone into the server sub-folder: `https://github.com/buscaroli/Futureproof-Lap1-GroupProject-Journal_Project_Backend`
- Repo to clone into the client sub-folder: `https://github.com/buscaroli/Journal_Project_Frontend`

```bash
  git submodule add https://github.com/buscaroli/Futureproof-Lap1-GroupProject-Journal_Project_Backend server

  git submodule add https://github.com/buscaroli/Journal_Project_Frontend client
```

You should now have a directory structure that looks like this;

```
docker-compose-exercise
|
|---- client
|
|---- server
|
.git
.gitmodules
```

It is now safe to use git from the main directory (docker-compose-exercise) as if you didn't have sub-folders containing .git folders are they will be ignored (unless you cd into the subfolder and use the git commands from within that folder).
