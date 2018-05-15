Xcode CLI Tools
-> xcode-select --install

Homebrew
-> installed via the interweb command

iTerm2
-> Downloaded and drag/dropped
-> Preferences->Profiles->General->Reuse previous session's directory

Oh My ZSH
-> uncommented .zshrc PATH setting to enable ~/bin

Git (check that it is installed, configure it)
-> which git
-> git config --global user.name "Karol S. Mazur"
-> git config --global user.email "my_email"

Sublime Text
-> linked subl to ~/bin/subl

Solarized Theme
-> download and installed color presents for iTerm2
-> turned on the dark solarized theme in iTerm2

GitUp
-> http://gitup.co
-> Install Command Line Tool

rbenv
-> brew install rbenv
-> add eval "$(rbenv init -)" to .zshrc

Optionally globally skip Ruby gem doc installation
-> echo "gem: --no-ri --no-rdoc" > ~/.gemrc

Installing gems globally vs. in the user directory
-> gem env
-> gem install rails --user-install (in this case the user bin needs to be in the PATH)

Setup GEM_HOME and GEM_PATH if necessary to avoid sudo'ing all the gems
-> https://stackoverflow.com/a/2619731

Installing gems per project
-> bundle install --path vendor/bundle
