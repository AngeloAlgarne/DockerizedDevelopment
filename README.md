# Dockerized Development
This is a template for dockerized development with VS Code.

## How it works

Instead of having all your packages installed in your local storage, have it all installed in one development container.
1. You must first have docker installed
2. Fork and clone this repository, or maybe just download the folder
3. Clone your project inside this _projects_ folder
4. Modify the docker templates and use them accordingly
5. You should now have a docker compose for your app, and a separate container for development
6. Start developing inside your container

## Directory
1. `.devcontainer` contains the json file used by VS Code to enable dockerized development.
2. `py_requirements.txt` are all the additional python packages.
3. `Dockerfile` and `compose.yml` is for running Odoo 16 server in Docker desktop.

# Setup
Follow the steps below to start the development process. Note that this project has only been tested in Windows.

## Requirements
1. Docker desktop ([installation guide](https://docs.docker.com/desktop/install/windows-install/ "How to install?"))
2. [VS Code](https://code.visualstudio.com/ "What's VS Code? How to install?")

## Steps to start
- Clone this git repository or download the folder.
- Clone your project inside the `projects/` folder.
- Copy one of the correspending compose and/or dockerfile for your project, found in `docker` folder, and paste it on the root folder.  Make sure that you change the docker filename setting in the `devcontainer.json` file.
- Open the terminal in the root folder and enter `docker compose up -d`. Make sure that `external: true` is __commented out__ in the **compose** file.
3. Uncomment the `external: true` to enable reattachment of the volumes, then run `docker compose build` and `docker compose up -d` in the same terminal.
4. Open VS Code and click the double bracket icon at the bottom left then select "*Reopen in Container*" and pick "*Existing Docker*" option. Once done, you should be able to see a new container with a random name. You can rename the container in command prompt with `docker rename <random_name> <new_name>`.
5. You should now be able to see the same files in the directory; you can now also exit the terminal.
6. Happy coding!

# Notes

## General
- To restart the server, just restart the docker container.
- Just to be safe, always push changes to a different branch other than `main`, and just pull-request it afterwards.
- To install new python dependencies, add it in `py_requirements.txt` and rebuild the container with `docker compose up -d` again. Make sure to check `compose.yml` > `volumes` > `external` is `true` to make use of the existing database.

## Workflow
Once the setup is done, you should now be able to work on the code. Some good rule of thumbs are the following.
1. Always `git pull` first before changing anything. You can also do this inside the dev container once the [setup](#Setup "Go to Setup") is done.  
2. Before pushing changes, you should be working in a different branch other than `main`, say,`dev`.


