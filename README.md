# VIM

This is the configuration I currently use for day to day development.
When I stop using or add new technologies to my stack they will be updated here.

**NOTE:** This vim configuration uses youcompleteme which requires gcc-8 and g++-8 to properly compile C++17.
The code below can be used to update your available gcc version on linux based operating systems.
```bash
sudo apt-get install g++-8
sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-7 700 --slave /usr/bin/g++ g++ /usr/bin/g++-7
sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-8 800 --slave /usr/bin/g++ g++ /usr/bin/g++-8
```

Or this on Mac OS

```zsh
brew install gcc@8
brew unlink gcc
brew link gcc@8
```


Additionally, youcompleteme requires a version of vim that is compiled with support for Python 3.
This condition can be satisfied by pulling the current code from the official [vim](https://github.com/vim/vim.git) github repository and then using the command bellow to set the config before installing vim using *Make*.

```bash
./configure --with-python3-command=python3.7 \
            --with-python3-config-dir=/usr/lib/python3.7/config-3.7m-x86_64-linux-gnu \
            ... (other config params) ...
```

**Warning: Buyer beware! Do not use this configuration if you are not familiar with the contents of the plugins and values set in the vimrc. Similarly, do not copy-and-paste commands provided on this *README.md* without researching how they will effect your environment and if you need them!**

