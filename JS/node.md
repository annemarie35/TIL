# NODE

## USE RIGHT VERSION IN YOU VERSION

- Install Node version with `NVM`
- Add a `.nvmrc` file in root directory, you can add the current version you use locally for exemple: 
```shell
    node -v > .nvmrc
```
- or add in the file:
```text
lts/*
```
- Keep an eye on last stable version (Lts) and new versions on [this page](https://nodejs.org/en/about/previous-releases)
- If you use `Zsh` you can add a script to load `.nvmrc` when exist in node project directory