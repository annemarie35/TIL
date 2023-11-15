# LINUX

## Example [from this fix](https://github.com/dotnet/sdk/issues/27129) on installing dotnet SDK 6.0 on ubuntu 23

I recently had to install .NET because the project's backend was in .NET
Some dependencies problems beetween Ubuntu 23 and .NET SDK 6.0 appears so i had to use this linux commands.

- Show more details on distribution installed on your machine
```shell
  cat /etc/*release 
```

### Change where to download packages from (one problem was i had download previously package from linux and other from microsoft)

- Remove first all i have installed before
Run `sudo apt remove --purge --autoremove *dotnet*` (*dotnet* this wild card works with bash but not zsh !)

create or `modify /etc/apt/preferences` and add (you'll need sudo)
```shell
sudo vi /etc/apt/preferences
```

and add in it : 
```
Package: *net*
Pin: origin packages.microsoft.com
Pin-Priority: 1001
```
Run `man apt_preferences` for more info about this config.

Run `sudo apt install dotnet-sdk-6.0`

- To see where dotnet is installed ` where dotnet`

