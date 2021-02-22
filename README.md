# VIM

This is the configuration I currently use for day to day development.
When I stop using or add new technologies to my stack they will be updated here.

## Install
If you want to use this file to lead your development as well follow the commands below in your environment:
```bash
cd ~/
git clone --recursive https://github.com/dedmonds784/.vim.git
ln -sf $HOME/.vim/vimrc $HOME/.vimrc
cd $HOME/.vim
git submodule update --init
```

## Bracey

If you find you want to do Web Development using Vim you can use [bracey](https://github.com/turbio/bracey.vim) to create a live server and view changes as you make them.

to run bracey run:

```vim
:Bracey
```

When you are done developing, or just want to stop the server run:

```vim
:BraceyStop
```

In order to force the current page you have open to reload run:

```vim
:BraceyReload
```

More configurations and commands can be found on the Bracey github.


## Remove Plugins

If you find that you want to remove a plugin from the environment reference the commands provided below.

Remove `foo` plugin:
```bash
cd ~/.vim
git submodule deinit pack/plugins/start/foo
git rm -r pack/plugins/start/foo
rm -r .git/modules/pack/plugins/start/foo
```

## Updating plugins

Update `foo` plugin:

```bash
cd ~/.vim/pack/plugins/start/foo
git pull origin main
```

It is recommend to `git fetch origin main` a plugins repository, and review changes before running `git merge`.

Update all plugins:

```bash
cd ~/.vim
git submodule foreach git pull origin master
```

Note, new commits to plugins create uncommited changes in the main repository.
So after any update in the submodule, you need to commit the main repository as well:

```bash
cd ~/.vim
git commit -am "Updated plugins."
```

If a `git pull` for the main repository leads to uncommited changes in the submodules as plugins were updated, you can run `git submodule update` to change the recorded state of the submodules.

Submodules can be complicated, but are required in order to maintain an easily-cloneable repository.
If you do not want to version control submodules at all add a new line `pack` to the repositories `.gitignore`, and manually add all plugins on a new machine.

**Warning: Buyer beware! Do not use this configuration if you are not familiar with the contents of the plugins and values set in the vimrc. Similarly, do not copy-and-paste commands provided on this *README.md* without researching how they will effect your environment and if you need them!**

