# Useful stuff on *nix systems

## Find file containing text in subfolders
```
grep -rnw --include=\*.{java,js} -rnw . -e "string you are looking for"
```
