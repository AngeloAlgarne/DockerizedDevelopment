# Dockerized Development
This is a template for dockerized development with VS Code.

## How it works

Instead of having all your packages installed in your local storage, have it all installed in one development container.
1. You must first have docker installed
2. Fork or clone this repository, or maybe just download the folder
3. Clone your project inside this _projects_ folder
4. Modify the docker templates and use them accordingly
5. You should now have a docker compose for your app, and a separate container for development
6. Start developing inside your container

## Directory
- `.devcontainer` contains the json file used by VS Code to enable dockerized development.

# Setup
Follow the steps below to start the development process. Note that this project has only been tested in Windows.

## Requirements
1. Docker desktop ([installation guide](https://docs.docker.com/desktop/install/windows-install/ "How to install?"))
2. [VS Code](https://code.visualstudio.com/ "What's VS Code? How to install?")

## Steps to start
- Fork or clone this git repository or download the folder.
- Clone your project inside the `./projects/` folder.
- Copy one of the correspending dockerfiles/compose found in `./dockerfiles/`, and paste it on the `./compose.yml`.
- Open the terminal in the root folder and enter `docker compose up -d`.
- MISSING STEP: DEVCONTAINER SETUP
- Open VS Code and click the double bracket icon at the bottom left then select "*Reopen in Container*" and pick "*Existing Docker*" option. Once done, you should be able to see a new container with a random name. You can rename the container in command prompt with `docker rename <random_name> <new_name>`.
- Happy coding!

# Notes

## General
- To restart the server, just restart the docker container.
- Just to be safe, always push changes to a different branch other than `main`, and just pull-request it afterwards.
- Database needs to be in the same docker compose in order to establish connection.

## Workflow
Once the setup is done, you should now be able to work on the code. Some good rule of thumbs are the following.
1. Always `git pull` first before changing anything. You can also do this inside the dev container once the [setup](#Setup "Go to Setup") is done.  
2. Before pushing changes, you should be working in a different branch other than `main`, say,`dev`.


# Foot Notes
> This is extremely confusing to do. Might be for niche use cases only, but I think I still want to try making this work even if it's not as necessary.
> <br>
> — Angelo Algarne
