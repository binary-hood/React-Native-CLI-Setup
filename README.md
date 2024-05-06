![Binaryhood](Logo/BinaryhoodLogo.png)

# React Native CLI Environment Setup

You will need Node, Watchman, the React Native command line interface, Xcode, Ruby and CocoaPods. This is documented in detail on the [React Native website](https://reactnative.dev/docs/environment-setup).

## Install Homebrew

First ensure that [Homebrew](https://brew.sh/) (Mac dependency manager) is installed on your Mac.

To install, run the following command from Terminal:

- Run `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`

## Install Xcode

[Xcode](https://developer.apple.com/xcode) is the IDE used for native iOS development. Installing this will also install the iOS Simulator, command line tools and other components needed to build and run iOS apps.

Alternatively you can install Xcode versions directly from [here](https://xcodereleases.com/).

## Install Node, NPM and NVM

Next, we'll install [Node.js](https://nodejs.org) and NPM (Recommended: Use [NVM](https://github.com/nvm-sh/nvm))

- Run `brew install nvm` to install Node Version Manager.
- Run `mkdir ~/.nvm`
- Run `nano ~/.zshrc` (or use Vim / preffered editor) and add these lines:

```
export NVM_DIR=~/.nvm
source $(brew --prefix nvm)/nvm.sh
```

## Install Yarn

Next we'll install [Yarn](https://classic.yarnpkg.com/lang/en/docs/install/) as our Javascript dependency manager.

- Run `brew install yarn` to install Yarn.

## Install Watchman

[Watchman](https://facebook.github.io/watchman) is a tool used to monitor file changes and allows hot reloading in React Native.

- Run `brew install watchman`

## Install Ruby

Ruby comes preinstalled on Mac. To check which version you have, run the command `ruby -v` in the terminal.

To install RVM, a Ruby version manager that allows you to switch between different versions of Ruby and download specific versions, follow the instructions at [RVM](https://rvm.io/rvm/install)

Install RVM

- Run `\curl -sSL https://get.rvm.io | bash`

To list all available Ruby versions you can Run the command `rvm list known`

Install Ruby with the following command:

- Run `rvm install ${version}`
- Run `rvm use ${version}`

After installing Ruby, close and reopen your terminal, then run the command `ruby -v` to verify your Ruby version matches the version listed in [.ruby-version](../.ruby-version).

If your Ruby version still fails to update, you can use [rbenv](https://github.com/rbenv/rbenv) to upgrade or download Ruby using Homebrew.

Run the following command in your terminal:

- Run `brew install rbenv ruby-build`
- Run `echo 'if which rbenv > /dev/null; then eval "$(rbenv init -)"; fi' >> ~/.zshrc`
- Run `source ~/.zshrc`

Install Ruby:

- Run `rbenv install ${version}`
- Run `rbenv global ${version}`

Reopen your terminal and run:

- Run `ruby -v`

This should update your Ruby version.

## CocoaPods

[CocoaPods](https://cocoapods.org) is a dependency manager for native iOS development. We'll install the latest version (`1.11.2`).

- Run `sudo gem install cocoapods`

If you encounter problems install cocoapods via Ruby Gems you can use Homebrew instead:

- Run `brew install cocoapods`

## Java Development Kit (JDK)

[JDK](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) provides tools for native Java and Android Development. Install v11+.

- The Zulu OpenJDK distribution offers JDKs for both Intel and M1 Macs. This will make sure your build are faster on M1 Macs compared to using an Intel-based JDK.

If you have already installed JDK on your system, make sure it is JDK 11 or newer.

```shell
brew tap homebrew/cask-versions
brew install --cask zulu17
```

To check all installed Java versions, run the following command which will list all the installed Java versions.

- Run `/usr/libexec/java_home -V`

To set a specific version, use the following command

- Run `echo export "JAVA_HOME=\\$(/usr/libexec/java_home -v 17.0.10)" >> ~/.zshrc`

If you want to use a different Java version, replace 17.0.10 with the desired version, such as 11

To check the currently used Java version, simply run the command `echo $JAVA_HOME`

## Android Studio and Android SDK

[Android Studio](https://developer.android.com/studio) is the IDE used for native Android Development.

- Download and install from [Android Developer](https://developer.android.com/studio)
- Once installed, install the Android 10 (Q) SDK by following the [React Native Setup Guide](https://reactnative.dev/docs/environment-setup).

## Configure ANDROID_HOME

The React Native tools require an ANDROID_HOME environment variable to be set up in order to build apps with native code.

Add the following to your Mac's `zsh` `~/.zshrc` or `bash ~/.bashrc` config file:

| Tip: If you're not sure which shell you have, you can run -> `echo $SHELL` to check

```
export ANDROID_HOME=$HOME/Library/Android/sdk
export PATH=$PATH:$ANDROID_HOME/emulator
export PATH=$PATH:$ANDROID_HOME/tools
export PATH=$PATH:$ANDROID_HOME/tools/bin
export PATH=$PATH:$ANDROID_HOME/platform-tools
```

Once all these tools have been installed, you are ready to setup the React Native project itself.
