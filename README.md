# taskfiles
A library of Taskfiles.

# Usage

## Git Submodule
A common way to use this is as a git submodule. In your repository simply initialize this repo as a submodule called `.taskfiles` and you can freely reference then in your repo's `Taskfile.yml`.

```shell
git submodule add https://github.com/frozenfoxx/taskfiles.git .taskfiles
```

You can now update with the latest version of the taskfiles by issuing the following the command:

```shell
git submodule update --init --recursive
```

To change the target branch, modify the `.gitmodules` file in your repository and update `branch` to the desired branch.

