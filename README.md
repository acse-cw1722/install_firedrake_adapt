# Install Firedrake with adaptive mesh function

## install command:

Run `source ./install_firedrake.sh` under project root folder. This will set up a folder for firedrake and relavent envs.

## For mac users:

One gotcha users could encounter is listed [here](https://github.com/firedrakeproject/firedrake/issues/2793) and If you are using gmake 4.4.1, you should run

```{shell}
brew tap-new $USER/local-make
brew extract --version=4.4 make $USER/local-make
brew install make@4.4
brew unlink make
brew link make@4.4
```

before executing the install script.

## Other settings

if you wish to set a command to activate firedrake instead of typing in a long path to your activate file, you could wirite following line to your .bash_rc or equivalent bash init file:

`alias fire_drake='source </path/to/your/acivate/file>'

then execute `fire_drake` in a new shell.

to deactivate, simply use `deactivate`.
