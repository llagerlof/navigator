# Navigator

Navigator is a script to allow fast and easy directory navigation.


## Features, tailored for best user experience

- The last created directories are near the focused cursor for quick access.
- Always focus on directory ".." when changing directory to allow quick exit to the parent directory.
- Files are listed separated from directories.
- Files can be opened with the associated application.
- Fuzzy finder.

![Captura de tela de 2022-11-22 13-17-15](https://user-images.githubusercontent.com/193798/203366322-41ea9424-c7b7-4e57-a06a-84bdb42edff8.png)


## Required dependency

- **fzf** - fuzzy finder. Your distro probably has it available to install. If not, go to https://github.com/junegunn/fzf


## Optional dependencies (recommended for best experience)

- **xclip** - reason: While inside the Navigator the current directory's path or last opened file's path is always copied to the clipboard.
- **xdg-open** (package xdg-utils) - reason: Allow the Navigator to open the selected file with the associated application.


## How to install

- Copy this script to `/usr/local/bin/`
- Make it executable with `chmod +x /usr/local/bin/navigator`
- Create an alias in your `~/.bashrc`. Add the following line to the end of file:
```
alias n="source /usr/local/bin/navigator"
```
- Reopen the shell to reload the aliases.


## How to use

- Run the script typing "n" in bash.
- Navigate with arrow keys.
- Press ENTER key to enter a directory.
- Press ENTER key to open a file with the associated application.
- Start typing to fuzzy search the current list of directories and files.
- ESC to exit the script. Your new current directory is the last directory visited while inside the Navigator.
