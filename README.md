# macos junk remover

## commands to clean up obsolete logs

```sh
# delete logs files wherever they are
find / -type f 2> /dev/null | grep '\.log$' | sed 's/[[:space:]]/\\\ /g' | xargs rm

# remove logs
sudo rm -rf /var/log/*.log

# remove trashed files permanently
sudo rm -rf ~/.Trash/*

# remove cache (temporary saved files)
rm -rf ~/Library/Caches/*

#
sudo rm -rf /private/var/folders/*

#
sudo atsutil databases -remove

# remove all cached DNS records
sudo dscacheutil -flushcache && sudo killall -HUP mDNSResponder

# remove thumbnails of quicklook
rm -rf $TMPDIR/../C/com.apple.QuickLook.thumbnailcache
```

## other cleanup commands

```sh
# remove caches from RAM
sudo purge

# remove old/obsolete packages/files
brew cleanup
```

## other helpful commands

```sh
# get all directories sorted by size
du -h -d 1 2> /dev/null | sort -hr

# get all files & directories, sorted by size
ls -AhlS
```

## available on

- [GitHub](https://github.com/abanoubha/macos-junk-remover)
- [GitLab](https://gitlab.com/abanoubha/macos-junk-remover)
- [CodeBerg](https://codeberg.org/abanoubha/macos-junk-remover)

