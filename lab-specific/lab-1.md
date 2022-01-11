Lab 1 FAQ
=========

## Can't clone from GitHub

### Problem

When attempting to clone your repository from GitHub, you receive this error:

```
remote: Support for password authentication was removed on August 13, 2021. Please use a personal access token instead.
remote: Please see https://github.blog/2020-12-15-token-authentication-for-git-operations/ for more information.
fatal: Authentication failed for 'https://github.com/cs100/lab-01---introduction-to-software-construction-tooling-username.git/'
```

### Solution

The lab manual hasn't been updated to reflect recent changes at GitHub. You can't clone using your username and password anymore for security reason.

There are two options:

 1. [Set up a personal authentication](https://github.com/settings/tokens). For this class, select all scopes so that you're not limited.
 2. Set up SSH

Most people on Slack used the token method.


## CMake Warning (dev)

### Problem

When running `cmake3 .`, this output appears:

```
CMake Warning (dev) in CMakeLists.txt:
  No project() command is present.  The top-level CMakeLists.txt file must
  contain a literal, direct call to the project() command.  Add a line of
  code such as

    project(ProjectName)

  near the top of the file, but after cmake_minimum_required().

  CMake is pretending there is a "project(Project)" command on the first
  line.
This warning is for project developers.  Use -Wno-dev to suppress it.
```

### Solution

The professor has confirmed that you can safely ignore this warning.


## CMake Cache Error

### Problem

When attempting to run `cmake3 .`, you receive this error message:

```
CMake Error: The current CMakeCache.txt directory [...] is different than the directory [...] where CMakeCache.txt was created. This may result in binaries being created in the wrong place. If you are not sure, reedit the CMakeCache.txt
```

### Solution

This usually happens when you rename your project folder. Deleting CMakeCache.txt will fix this.


## make: 'area_calculator' is up to date.

### Problem

When running `make`, you receive the following output instead of a build progress monitor:

```
make: 'area_calculator' is up to date.
```

### Solution

You can ignore this message. One of the purposes of Makefiles is to avoid unnecessary compilations. This message is telling you that the source files haven't changed since `make` was last run, so there's nothing to recompile.


## Makefile Missing Separator

### Problem

Writing the `Makefile`, you receive the following error when attempting to build it:

```
Makefile:2: *** missing separator.  Stop.
```

### Solution

This is an indentation issue. [Using tab characters instead of four spaces can fix it](https://stackoverflow.com/a/14109796).


## Compilation Errors from `googletest`

### Problem

After adding the `googletest` submodule to your repository, you receive compilation errors when you try to build it with `make`

### Solution

#### Solution #1

This will restore [an older version of `googletest`](https://github.com/google/googletest/commit/f966ed) that is more likely to work.

```bash
pushd googletest ; git checkout f966ed ; popd
```

#### Solution #2

You may have forgotten to add the updated tools mentioned in the section about `.bashrc`. These errors are caused becaues the default version of `g++` is too old to build the `googletest` module.
