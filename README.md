# Dockerized Development
This is a template for dockerized development with VS Code.

## How it works
1. You must first have docker installed
2. Fork and clone this repository, or maybe just download the folder
3. Clone your development folder inside this root folder
4. Modify the docker templates and use them accordingly
5. After completing the setup below, you should be able to develop inside docker.

## Directory
1. `.devcontainer` contains the json file used by VS Code to enable dockerized development.
2. `py_requirements.txt` are all the additional python packages.
3. `Dockerfile` and `compose.yml` is for running Odoo 16 server in Docker desktop.

# Setup
Fllow the steps below to start the development process. Note that this project has only been tested in Windows.

## Requirements
1. Docker desktop ([installation guide](https://docs.docker.com/desktop/install/windows-install/ "How to install?"))
2. [VS Code](https://code.visualstudio.com/ "What's VS Code? How to install?")

## Steps to start
1. Clone this git repository or download the folder, then clone your project inside the `project` folder.
2. Open the terminal and enter `docker compose up -d`. Make sure that `external: true` is commented out in the `compose` file.
3. Uncomment the `external: true` so that data is saved regardless of the container, then run `docker compose build` and `docker compose up -d` in the same terminal.
4. Open VS Code and click the double bracket icon at the bottom left then select "*Reopen in Container*" and pick "*Existing Docker*" option. Once done, you should be able to see a new container with a random name. You can rename the container in command prompt with `docker rename <random_name> <new_name>`.
5. You should now be able to see the same files in the directory. At this point, you can also close the terminal.
6. Start coding inside the `extra-addons` directory.

# Notes

## General
- To restart the server, just restart the docker container.
- Just to be safe, always push changes to a different branch other than `main`, and just pull-request it afterwards.
- To install new python dependencies, add it in `py_requirements.txt` and rebuild the container with `docker compose up -d` again. Make sure to check `compose.yml` > `volumes` > `external` is `true` to make use of the existing database.

## Workflow
Once the setup is done, you should now be able to work on the code. Some good rule of thumbs are the following.
1. Always `git pull` first before changing anything. You can also do this inside the dev container once the [setup](#Setup "Go to Setup") is done.  
2. Before pushing changes, you should be working in a different branch other than `main`, say,`dev`.


