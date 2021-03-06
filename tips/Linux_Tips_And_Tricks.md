# Linux Tips and Tricks

## Find and delete files

* `find . -name "*.bak" -type f -delete`
* `find . -name "*.bak" -type f -print0 | xargs -0 /bin/rm -f`

## Find and delete folders

* `find . -name test -type d -print0|xargs -0 rm -r --`
* `find . -name test -type d -exec rm -r {} \;`
* `find . -name test -type d -exec rm -r {} +`
* `find . -name "test" -type d -delete`
* `find . "test" -type d -exec rm -rf {} \;`
* `find . -name test -exec rm -R "{}" \;`


## chmod all files and directories recursively
```
find . -type d -exec chmod 755 {} \;
find . -type f -exec chmod 644 {} \;
```

## Truncate all files in a directory
```
for f in *; do >$f; done
```
