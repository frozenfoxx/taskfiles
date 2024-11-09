# taskfiles
A library of Taskfiles.

# Usage

## Git Clone
The most straightforward way to use this is by simply cloning the repository into your repo, then you can reference the taskfiles herein. To do this you could clone directly. A more robust solution though is to add this into your repo's `Taskfile.yml`, usually as part of an `update` mechanism.

_Taskfile.yml_:
```shell
[...]
includes:
  [reference name]:
    taskfile: .taskfiles/[reference name].tasks.yml
    optional: true
    internal: true

[...]
tasks:
  update:
    desc: "Update repo"
    cmds:
      - rm -rf .taskfiles
      - git clone https://github.com/frozenfoxx/taskfiles.git .taskfiles
      - git pull --rebase
```

Be sure to add it into the `.gitignore`:

```shell
.taskfiles
```

Then run the `update` task:

```shell
task update
```

## Git Submodule
A common way to use this is as a git submodule. In your repository simply initialize this repo as a submodule called `.taskfiles` and you can freely reference then in your repo's `Taskfile.yml`.

```shell
git submodule add https://github.com/frozenfoxx/taskfiles.git .taskfiles
```

You can now update with the latest version of the taskfiles by issuing the following the command:

```shell
task update
```

Alternatively, you can update with the following git command:

```shell
git submodule update --init --recursive
```

To change the target branch, modify the `.gitmodules` file in your repository and update `branch` to the desired branch.

## Tasks

There are also some tasks available directly:

```shell
task
```
