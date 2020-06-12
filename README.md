# Strap Template

This repo aims to be a simple and straightforward way to begin persisting and your development environment. You are encouraged to fork this repo and make it your own! The simple architecture of this repo will get you most of what you want and need in creating a persistent and reproducible development environment, that can be recreated on a fresh computer with 1 command.

## Strap - the foundation

This template uses [Strap](https://github.com/MikeMcQuaid/strap) as the foundation for creating a reproducible development environment. Please read the README for the strap project.

## How to use

### Brewfile

After strap is run, there will be symlink in your home directory `~/.Brewfile` that will be linked to `dot/Brewfile` inside of this repo. The location of `~/.Brewfile` is the expected location of the `brew bundle --global` command, which will magically download and install all of the software enumerated in your Brewfile.

We recommend that you use this ongoing with the following steps. Rather than simply running `brew install xyz` you can persist this long term by:

```
# Add the software to your `~/.Brewfile`
brew 'ag'

# Install all of the software on your Brewfile (including the change you just made)
brew bundle --global

# Commit your dotfiles repo. Because your home directory .Brewfile is symlinking to your dotfiles repo, your modification will be known to git and ready to be added and committed.
git commit -am "Added ag to Brewfile"
```

Following this method will give you a versioned declaritive definition of your system software, reproducible and available to you for the long term.

Brew bundle is the best way to persist your MacOS system software. Read more about it, and the file format for `Brewfile` here: https://github.com/Homebrew/homebrew-bundle.

## Project Structure

### `script`

The script dir contains two files, `setup` and `strap-after-setup`. These files are both called from [Strap](https://github.com/MikeMcQuaid/strap) during it's execution. You can read more about when these files are executed in the strap docs, but to simply 




