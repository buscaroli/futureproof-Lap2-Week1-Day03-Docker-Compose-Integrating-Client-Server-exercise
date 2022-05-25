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

#### Amend the .gitmodules file

It is recommended to change the path of each submodule to a relative path, make them look like this:

```
[submodule "client"]
	path = client
	url = ../Journal_Project_Frontend.git
[submodule "server"]
	path = server
	url = ../Futureproof-Lap1-GroupProject-Journal_Project_Backend.git
```

## Create a docker-compose.yaml file

We originally used python's http.server to run the clinet, I have now installed npm's http-server and modified the package.json in the client/ folder to reflect this. the reason I did this is that not everybody has python installed in their computer, this way http-server will be installed with the rest of the dependencies and the app will be available at localhost:8080.

## How to run

I have given this repo a very long name, apologies for that.
In order to run it clone it and then follows these steps:

```bash
  cd futureproof-Lap2-Week1-Day03-Docker-Compose-Integrating-Client-Server-exercise
  docker compose up

```

Now you can open your browser to the address `localhost:8080`.
