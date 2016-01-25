# Useful stuff on *nix systems

## Find file containing text in subfolders
```
grep -rn --exclude-dir=node_modules --exclude-dir=bower_components --include=\*.{java,js} . -e "string you are looking for"
```
