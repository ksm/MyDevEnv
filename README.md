Notes on setting up my developer environment. These may one day serve as a launch pad for automating the setup process, but for now these are Good Enough™.

## Xcode CLI Tools
- `xcode-select --install`

## Xcode Themes
- https://github.com/ArtSabintsev/Solarized-Dark-for-Xcode
- https://github.com/nelsyeung/Solarized-Light-for-Xcode

## VS Code
- brew cask install visual-studio-code
- https://code.visualstudio.com/docs/setup/mac#_launching-from-the-command-line

## Homebrew
- `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`

## iTerm2
- `brew cask install iterm2`
- Preferences->Profiles->General->Working Directory->Advanced Configuration->Reuse previous session's directory for New Tabs
- Preferences->Profiles->Colors->Color Presents->Solarized

## Oh My ZSH
- uncomment .zshrc PATH setting to enable ~/bin
- more .zshrc things:
alias gs='git status '
alias ga='git add '
alias gb='git branch '
alias gc='git commit'
alias gd='git diff'
alias go='git checkout '
alias gx='gitup'
alias gf='git fetch'
alias gl='git log'
alias gh='git log --graph --pretty=format:"%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset" --abbrev-commit --date=relative'
alias ghp='git log --graph --pretty=format:"%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset" --abbrev-commit --date=relative -p'

## Configure Git
- git config --global user.name "Karol S. Mazur"
- git config --global user.email "my_email"

## Dash
- https://kapeli.com/dash
- Install relevant docsets
- Set global search shortcut to CMD+Return

## GitUp
- http://gitup.co
- Install Command Line Tool

## rbenv
- brew install rbenv
- rbenv init
- add eval "$(rbenv init -)" to .zshrc
- verify it works: curl -fsSL https://github.com/rbenv/rbenv-installer/raw/master/bin/rbenv-doctor | bash

## Skip Ruby gem doc installation globally
- echo "gem: --no-ri --no-rdoc" > ~/.gemrc
- or include ri -> echo "gem: --no-rdoc" > ~/.gemrc

Installing gems per rbenv ruby version vs. globally vs. in the user directory:
- gem env
- best practice right now: rbenv install newest ruby version and set, then install relevant gems. this avoids the need for sudo.
- e.g. gem install rails --user-install (in this case the user bin needs to be in the PATH)
- Optionally setup GEM_HOME and GEM_PATH to avoid sudo: https://stackoverflow.com/a/2619731
- gem install bundler --user-install

Installing gems per project
- bundle install --path vendor/bundle

## Insomnia (or Paw)
- brew cask install insomnia
- https://insomnia.rest
- https://paw.cloud

## Nocturnal
- https://github.com/HarshilShah/Nocturnal
- brew cask install nocturnal
- configure so it starts with every login

## nvALT
-> http://brettterpstra.com/projects/nvalt/#dl

## Sublime Text (Using VS Code instead for now)
- mkdir ~/bin; ln -s /Applications/Sublime\ Text.app/Contents/SharedSupport/bin/subl ~/bin/subl
- install Package Control
- install Open URL
- install DashDoc
- install CloseOtherWindows
- install AllAutocomplete
- install AdvancedNewFile
- settings:
```
  {
    "font_face": "Monaco",
    "font_size": 15,
    "tab_size": 2,
    "translate_tabs_to_spaces": true,
    "folder_exclude_patterns": ["tmp"],
  }
```
- keymap below:
```
[
  { "keys": ["super+shift+j"], "command": "reveal_in_side_bar" },
  { "keys": ["ctrl+super+left"], "command": "jump_back" },
  { "keys": ["shift+super+w"], "command": "close_other_tabs"},
  { "keys": ["ctrl+h"], "command": "dash_doc"}
]
```
