```
%fs ls < directory name >
```

```
%fs ls < directory name > / < subdirecory name >
```

```
dbutils.fs.ls(< directory name >)
```

```
for <file> in dbutils.fs.ls(< directory name >):
    print(file)
```

```
for <file> in dbutils.fs.ls(< directory name >):
    print(file.path)
```