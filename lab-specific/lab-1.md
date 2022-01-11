Lab 1 FAQ
---------

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

You may haven't added the updated tools mentioned in the section about `.bashrc`. These errors are caused becaues the default version of `g++` is too old to build the `googletest` module.
