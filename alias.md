## Aliased commands

### List aliases
```
git config --global alias.alias 'config --get-regexp ^alias'
```

### Add all files except test Java test files
```
git config --global alias.nt 'add . -- ":!src/test/*"'
```

### Log graph
```
git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset - %Cgreen%<(16)%ah%Creset %C(bold blue)%<(16)<%an>%Creset %C(auto)%d%Creset%s' --abbrev-commit"
```

### Log one-line with date
```
git config --global alias.ol "log --pretty=format:'%C(auto)%h%Creset %Cgreen%<(16)%ah%Creset %C(auto)%d%Creset %s'"

### Log one-line, limit to today's commits

```
git config --global alias.olt "log --pretty=format:'%C(auto)%h%Creset %Cgreen%<(16)%ah%Creset %C(auto)%d%Creset %s' --since='1 hour'"
```

### Log one-line, limit to yesterday's commmits

```
git config --global alias.olt "log --pretty=format:'%C(auto)%h%Creset %Cgreen%<(16)%ah%Creset %C(auto)%d%Creset %s' --since='24 hour' --until='3 hour'"
```
