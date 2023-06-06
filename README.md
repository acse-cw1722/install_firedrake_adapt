# Install Firedrake with adaptive mesh function

This is a repo containing scripts to install firedrake with adaptive mesh function.

Most of the materials comes from [pyroteus](https://github.com/pyroteus/pyroteus/tree/main/install) and [firedrake](https://github.com/firedrakeproject).

If you are using conda, it is the best to deactivate it before running the installation by using (`conda deactivate`)

## Install:

1. Replace `SOFTWARE=<your/install/path>` in `install_firedrake.sh` to the project root folder (where you can find `install_firedrake.sh` and `petsc_options.txt`).


2. Run `source ./install_firedrake.sh` under project root folder. This will set up a folder for firedrake and relavent envs.

## For mac users:

### `-w` error in making PETSc

One gotcha users could encounter is listed [here](https://github.com/firedrakeproject/firedrake/issues/2793) so if you are using gmake 4.4.1, you should run

```{shell}
brew tap-new $USER/local-make
brew extract --version=4.4 make $USER/local-make
brew install make@4.4
brew unlink make
brew link make@4.4
```

before executing the install script.

Note this is caused by a bug produced by gmake 4.4.1, so in the future, if gmake get around with this bug, you do not necessarily need to do this step.

PS: some users reflected that the `4.4` should be replaced with `4.4.0`. If the above instructions failed, please use `4.4.0` instead of `4.4`

### Parallel error

After installation, if you find parallel tests are failing, then please do some editing as suggested [here](https://firedrakeproject.org/download.html#testing-the-installation)

To be more specific, add below statement in `/etc/hosts` (if not editable, use sudo vim /etc/hosts to force writting)

(use `hostname` command to find LOCALHOSTNAME and the LOCALHOSTNAME below)

```
127.0.0.1       LOCALHOSTNAME.local
127.0.0.1       LOCALHOSTNAME
```

# Activate firedrake

firedrake installation come along with a virtual env. To use firedrake, you need to activate it by doing:

`source /path/to/firedrake/src/firedrake_adapt/bin/activate`

## Other settings

if you wish to set a command to activate firedrake instead of typing in a long path to your activate file, you could wirite following line to your .bash_rc or equivalent bash init file:

`alias fire_drake='source </path/to/your/acivate/file>'

then execute `fire_drake` in a new shell.

to deactivate, simply use `deactivate`.

