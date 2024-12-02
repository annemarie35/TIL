# SSH

The github tutorial is nice to follow.
One useful tips when for example, you want to use two github accounts, one pro and on personnal for example.
Juste remove all keys

```shell
ssh-add -D   
```

Then add just the one you need :
```shell
ssh-add ~/.ssh/id_rsa
```