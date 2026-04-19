# Navigator

Navigator is a script to allow fast and easy directory navigation.


## Features, tailored for best user experience

- The last created directories are near the focused cursor for quick access.
- Always focus on directory ".." when changing directory to allow quick exit to the parent directory.
- Files are listed separated from directories.
- Files can be opened with the associated application.
- Fuzzy search.

![Captura de tela de 2022-11-25 12-24-28](https://user-images.githubusercontent.com/193798/204015683-85bbe328-ec2f-497e-9b54-89f3f625daf7.png)


## Required dependency

- **fzf** - reason: fuzzy search (Your distro probably has it available to install. If not, go to https://github.com/junegunn/fzf)


## Optional dependencies (recommended for best experience)

- **xclip** - reason: While inside the Navigator the current directory's path or last opened file's path is always copied to the clipboard.
- **xdg-open** (package xdg-utils) - reason: Allow the Navigator to open the selected file with the associated application.


## Installation

Navigator needs to be **sourced** from your shell so it can change your current directory. After installing the script, add an alias like this to `~/.bashrc`:

```bash
alias n="source /path/to/navigator"
```

Then reopen your shell, or run `source ~/.bashrc`.

### Install only for the current user

#### Option 1: clone the repository and symlink the script into `~/.local/bin`

```bash
mkdir -p ~/repos ~/.local/bin
git clone https://github.com/llagerlof/navigator.git ~/repos/navigator
chmod +x ~/repos/navigator/navigator
ln -s ~/repos/navigator/navigator ~/.local/bin/navigator
echo 'alias n="source ~/.local/bin/navigator"' >> ~/.bashrc
source ~/.bashrc
```

If you prefer, you can replace `~/repos` with `~/repositories`.

#### Option 2: download the script directly into `~/.local/bin`

```bash
mkdir -p ~/.local/bin
curl -fsSL https://raw.githubusercontent.com/llagerlof/navigator/master/navigator -o ~/.local/bin/navigator
chmod +x ~/.local/bin/navigator
echo 'alias n="source ~/.local/bin/navigator"' >> ~/.bashrc
source ~/.bashrc
```

### Install for everyone

#### Option 3: clone the repository into a normal user's home directory and symlink it into `/usr/local/bin`

```bash
mkdir -p ~/repos
git clone https://github.com/llagerlof/navigator.git ~/repos/navigator
chmod +x ~/repos/navigator/navigator
sudo ln -s ~/repos/navigator/navigator /usr/local/bin/navigator
echo 'alias n="source /usr/local/bin/navigator"' >> ~/.bashrc
source ~/.bashrc
```

If you prefer, you can replace `~/repos` with `~/repositories`. Make sure other users can read and execute the cloned directory if they need to use the shared symlink.

#### Option 4: download the script directly into `/usr/local/bin`

```bash
sudo curl -fsSL https://raw.githubusercontent.com/llagerlof/navigator/master/navigator -o /usr/local/bin/navigator
sudo chmod +x /usr/local/bin/navigator
echo 'alias n="source /usr/local/bin/navigator"' >> ~/.bashrc
source ~/.bashrc
```


## How to use

- Run the script typing "n" in bash.
- Navigate with arrow keys.
- Press ENTER key to enter a directory.
- Press ENTER key to open a file with the associated application.
- Press ESC key to exit the script. Your new current directory is the last directory visited while using Navigator.
- Start typing to fuzzy search the current list of directories and files.
