# Viewing the Commit History

## After you have created several commits, or if you have cloned a repository with an existing commit history, you’ll probably want to look back to see what has happened. The most basic and powerful tool to do this is the `git log` command.

### `--stat` option prints below each commit entry a list of modified files, how many files were changed, and how many lines in those files were added and removed. It also puts a summary of the information at the end.

### `--pretty`. This option changes the log output to formats other than the default. A few prebuilt option values are available for you to use the 

- `oneline` value for this option prints each commit on a single line, which is useful if you’re looking at a lot of commits. In addition, the 
- `short`, 
- `full`, and 
- `fuller` values show the output in roughly the same format but with less or more information, respectively:
- `git log --pretty=oneline`

### The most interesting option value is `format`, which allows you to specify your own log output format. This is especially useful when you’re generating output for machine parsing — because you specify the format explicitly, you know it won’t change with updates to Git:
- `git log --pretty=format:"%h - %an,  %ar : %s"`
- `%an` Author name
- `%h` Abbreviated commit hash
- `%ar`	Author date, relative
- `%s`Subject


















