Notes on setting up my developer environment. These may one day serve as a launch pad for automating the setup process, but for now these are Good Enough™.

## General macOS settings

- Mission Control-Automatically rearrange spaces-off

## Xcode CLI Tools

- `xcode-select --install`

## Homebrew

- `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`

## iTerm2

- `brew cask install iterm2`
- Preferences
  - Appearance -> General -> Theme -> Minimal
  - Profiles
    - General -> Working Directory -> Advanced Configuration -> Reuse previous session's directory for New Tabs and Split Panes
    - Colors -> Color Presets -> Dracula
    - Text -> Configure for Fira Code and see how it goes

## Xcode

- https://developer.apple.com/download/more/

## VS Code

- brew cask install visual-studio-code
- https://code.visualstudio.com/docs/setup/mac#_launching-from-the-command-line

## Fonts and themes

- FiraCode
  - https://github.com/tonsky/FiraCode
  - https://github.com/tonsky/FiraCode/wiki/Installing#macos
  - https://github.com/tonsky/FiraCode/wiki#how-to-enable-ligatures
- Dracula
  - https://draculatheme.com
  - mkdir ~/Themes
  - https://draculatheme.com/iterm
  - https://draculatheme.com/visual-studio-code
  - https://draculatheme.com/xcode

## VSCode settings.json

Editor settings

```json
{
  "editor.tabSize": 2,
  "editor.fontSize": 13,
  "editor.fontFamily": "FiraCode-Retina",
  "editor.fontLigatures": true,
  "editor.formatOnSave": true,
  "window.zoomLevel": 1
}
```

More streamlined VSCode

```json
{
  "editor.minimap.enabled": false,
  "breadcrumbs.enabled": false,
  "git.decorations.enabled": false,
  "explorer.openEditors.visible": 0,
  "workbench.fontAliasing": "antialiased",
  "zenMode.fullScreen": true,
  "workbench.activityBar.visible": false,
  "editor.matchBrackets": "never",
  "editor.renderLineHighlight": "none",
  "editor.renderIndentGuides": false,
  "editor.renderControlCharacters": false,
  "workbench.sideBar.location": "right",
  "scm.diffDecorationsGutterVisibility": "hover",
  "editor.glyphMargin": false,
  "editor.folding": true,
  "window.title": "${activeEditorMedium}${separator}${rootName}"
}
```

Other settings

````json
{
  "typescript.validate.enable": false,
  "javascript.validate.enable": false,
  "javascript.format.enable": false,
  "eslint.alwaysShowStatus": true,
  "eslint.packageManager": "yarn",
  "prettier.eslintIntegration": true,
  "git.autorefresh": false,
  "solargraph.useBundler": true,
}

Flow magic

```json
{
  "flow.pathToFlow": "${workspaceFolder}/node_modules/flow-bin/vendor/flow.cmd",
}
````

Ye olde settings:

```json
{
  "editor.multiCursorModifier": "alt",
  "workbench.iconTheme": "ayu"
}
```

## VSCode keybindings.json

```json
{
  "key": "cmd+t",
  "command": "workbench.action.terminal.toggleTerminal"
},
{
  "key": "cmd+t",
  "command": "workbench.action.terminal.focus",
  "when": "!terminalFocus"
},
{
  "key": "ctrl+cmd+e",
  "command": "editor.action.changeAll",
  "when": "editorTextFocus && editorTextFocus && !editorReadonly"
},
{
  "key": "ctrl+cmd+left",
  "command": "workbench.action.navigateBack"
},
{
  "key": "ctrl+cmd+right",
  "command": "workbench.action.navigateForward"
},
```

## VSCode Extensions

- Apollo GraphQL
- AutoTrim
- Babel JavaScript (mgmcdermott.vscode-language-babel)
- Color Highlight (naumovs.color-highlight)
- ESLint (dbaeumer.vscode-eslint)
- Flow Language Support (flowtype.flow-for-vscode)
- Git Blame
- npm Intellisense
- Path Intellisense
- Prettier
- Ruby Solargraph
- VSCode Ruby
- Live Share
- Markdown Preview GitHub Styling

## Oh My ZSH

- https://github.com/ohmyzsh/ohmyzsh
- uncomment .zshrc PATH setting to enable ~/bin
- more .zshrc things:

```sh
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
```

## Configure Git

- git config --global user.name "Karol S. Mazur"
- git config --global user.email "my_email"

## Hub

- `brew install hub`
- then use e.g. `hub clone MyDevEnv`

## Dash

- https://kapeli.com/dash
- Install relevant docsets
- Set global search shortcut to CMD+Return

## Divvy

- https://mizage.com/divvy/
- Settings -> Keyboard -> Shortcuts -> Input Sources -> Turn off CTRL+Space
- Use CTRL+Space for the global shortcut
- Basic Divvy shortcuts: 50% Left, 50% Right, Full Screen

## GitUp

- http://gitup.co
- Install Command Line Tool
- `ssh-add` fixes the ssh no callback set error

## rbenv

- `brew install rbenv`
- `rbenv init`
- add `eval "$(rbenv init -)"` to .zshrc
- verify it works: `curl -fsSL https://github.com/rbenv/rbenv-installer/raw/master/bin/rbenv-doctor | bash`

## Configure Ruby gem installation globally to avoid installing docs

- echo "gem: --no-ri --no-rdoc" > ~/.gemrc
- or include ri -> echo "gem: --no-rdoc" > ~/.gemrc

## Ruby

- install newest Ruby w/ rbenv

### Additional Ruby things

- `gem install bundler`
- Installing gems per rbenv ruby version vs. globally vs. in the user directory:
  - gem env
  - best practice right now: rbenv install newest ruby version and set, then install relevant gems. this avoids the need for sudo.
  - e.g. gem install rails --user-install (in this case the user bin needs to be in the PATH)
  - Optionally setup GEM_HOME and GEM_PATH to avoid sudo: https://stackoverflow.com/a/2619731
  - `gem install bundler --user-install`
- Installing gems per project
  - `bundle install --path vendor/bundle`

## nvm

- https://github.com/nvm-sh/nvm
- `curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.34.0/install.sh | bash`
- verify it works with: `command -v nvm`
- `nvm install node` to download, compile, and install the latest node

## Insomnia

- brew cask install insomnia
- https://insomnia.rest

## GraphiQL

- brew cask install graphiql

## Nocturnal

- https://github.com/HarshilShah/Nocturnal
- brew cask install nocturnal
- configure so it starts with every login

# Ye Olde Tooling

## Xcode Themes

- https://github.com/ArtSabintsev/Solarized-Dark-for-Xcode
- https://github.com/nelsyeung/Solarized-Light-for-Xcode
