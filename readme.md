# Taskfile

This is a taskfile containing a collection of commands for various tasks, such as:

- Setting up a new compute instance
- Creating a new repository based on cookiecutter
- Setting up a repository for use (including setting up the python environment)

Compared to following the confluence documentation, this taskfile will automates as many tasks as possible.
Additionally, for some, by going through all tasks step-by-step makes it easier to follow everything and not forget something.

## Why github?

I cannot get the remote taskfile part working with devops (both https with pat and ssh), and all examples only use github.

## Installation

1. Install taskfile: `sudo snap install task --classic`
2. Enable remote taskfiles: `echo 'export TASK_X_REMOTE_TASKFILES=1' >> ~/.bashrc​`
3. Restart terminal/shell, or run: `export TASK_X_REMOTE_TASKFILES=1`
4. Run a task with `task --taskfile https://github.com/JoeriA/aa_taskfile.git//taskfile.yml?ref=main TASK_NAME`. See below for more examples.

### VScode plugin

- Recommended to install the vscode extension 'taskfile-launcher' (the official 'task' extension does not work yet with mounted disks).

## Overview of tasks

In `taskfile.yml` you can find most important task and 'main' tasks calling subtasks.
Those subtasks are located in separate taskfiles in the `tasks` directory, loosely structured per theme.
You can call a subtask directly by refering to `FOLDER_NAME:SUBTASK_NAME` if necessary.

You can add arguments to a task by appending `KEY=VALUE` to the command. Below only the important arguments are showed, see the taskfiles for more information.

### setup_compute_instance

To do.

#### setup_compute_instance:reinstall_code_tunnel_service

When code tunnel service doesn't work anymore (login token expired)

### create_new_repo

Create new git repo based on raptor.

Arguments:
- REPO_TYPE: package_repo (default), project_repo

### setup_repo

Setup the current git repo: creating python environment, installing precommit, etc.

Arguments:
- REPO_TYPE: package_repo (default), project_repo

## Resources

* [Taskfile website](https://taskfile.dev)
* [Documentation remote taskfiles](https://taskfile.dev/docs/experiments/remote-taskfiles)
