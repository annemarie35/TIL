# SSH

The GitHub tutorial is nice to follow.
One useful tips when, for example, you want to use two GitHub accounts, one pro and on personal for example.
Just remove all keys

```shell
ssh-add -D   
```

Then add just the one you need :
```shell
ssh-add ~/.ssh/id_rsa
```