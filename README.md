# Coding Standards

## Commit message guidelines

### Format
```
<type>(<scope>): <subject>

<body>

<footer>
```

### Type
One of the following:

| Emoji        | Emoji code      | Description                  | Change to functionality / appearance | Change to meaning of production code |
| ------------ | --------------- | ---------------------------- | ----------------------- | ------------------------------------ |
| :star:       | `:star:`        | New feature                  | :heavy_check_mark:      | :heavy_check_mark:                   |
| :bug:        | `:bug:`         | General bugfix               | :heavy_check_mark:      | :heavy_check_mark:                   |
| :lock:       | `:lock:`        | Security feature / bugfix    | :heavy_check_mark:      | :heavy_check_mark:                   |
| :recycle:    | `:recycle:`     | General refactoring          | :x:                     | :heavy_check_mark:                   |
| :zap:        | `:zap:`         | Performance- / memory-related refactoring | :x:  | :heavy_check_mark:                   |
| :art:        | `:art:`         | Formatting, white space, renaming variables etc | :x:  | :x:                                  |
| :pencil:     | `:pencil:`      | Documentation, code comments | :x:                     | :x:                                  |
| :mag:        | `:mag:`         | Writing, refactoring, fixing automated tests | :x:     | :x:                                  |
| :wrench:     | `:wrench:`      | Build scripts, CI, gitignore, other chore       | :x:  | :x:                                  |
