# Dotfiles

Personal dotfiles for Steven Radack, designed to work across all systems.

## What's Included

- **Bash**: Shell configuration (`.bash_profile`, `.bashrc`)
- **Vim**: Editor configuration and plugins (`.vim/`, `.vimrc`)
- **Git**: Version control configuration (`.gitconfig`)
- **Tmux**: Terminal multiplexer configuration (`.tmux.conf`)

## Installation

Clone this repository to your home directory and run the install script:

```bash
cd ~
git clone <repository-url> dotfiles
cd dotfiles
./bin/install
```

The install script will:
- Create symlinks from your home directory to the dotfiles
- Back up any existing configuration files with a `.bak` extension
- Optionally download and install vim-plug for Vim plugin management

## Structure

```
dotfiles/
├── bash/
│   ├── bash_profile
│   └── bashrc
├── vim/
│   ├── vimrc
│   ├── gvimrc
│   └── autoload/
├── git/
│   └── gitconfig
├── tmux/
│   └── tmux.conf
└── bin/
    ├── install
    └── uninstall
```

## Post-Installation

After installation, the following symlinks will be created in your home directory:

- `~/.bash_profile` → `~/dotfiles/bash/bash_profile`
- `~/.bashrc` → `~/dotfiles/bash/bashrc`
- `~/.vim` → `~/dotfiles/vim`
- `~/.gitconfig` → `~/dotfiles/git/gitconfig`
- `~/.tmux.conf` → `~/dotfiles/tmux/tmux.conf`

### Vim Plugins

If you installed vim-plug during setup, run the following command in Vim to install plugins:

```vim
:PlugInstall
```

## Updating

Since the dotfiles are symlinked, any changes made to files in the `~/dotfiles` directory will immediately take effect. To update from the repository:

```bash
cd ~/dotfiles
git pull
```

## Uninstallation

To remove the dotfiles and restore your backups, run the uninstall script:

```bash
cd ~/dotfiles
./bin/uninstall
```

The uninstall script will:
- Remove all dotfile symlinks from your home directory
- Automatically restore any `.bak` backup files that were created during installation
- Prompt for confirmation before making changes

To completely remove the dotfiles directory after uninstalling:

```bash
rm -rf ~/dotfiles
```
