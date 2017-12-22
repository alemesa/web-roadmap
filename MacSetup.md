Ease up the development setup process - this guide is for Mac if you're on Windows I wish you good luck :P

* [Start](#start)
* [Fonts](#fonts)
* [iTerm2](#iterm2)
* [Homebrew](#homebrew)
* [Bash](#bash)
* [Git](#git)
* [VSCode](#vscode)
* [Node](#node)
* [Mongo](#mongo)
* [Others](#others)
* [Python](#python)
* [Heroku](#heroku)

### Start

---

#### _Start Here Please_

First thing you need to do, on any OS actually, is update the system! For that: **Apple Icon** > **About This Mac** then **Software Update**....

"Quality of Life" changes:

* Instal XCode Suite (even if you don't need it anymore you will probably need along the road)

```bash
xcode-select --install
```

* Install [Google Chrome](www.google.com/chrome) (Make it default)

### Fonts

---

#### _Better Fonts for Development_

These fonts are extremely readable:

* FiraCode (free) - [link](https://github.com/tonsky/FiraCode)
* Hack (free) - [link](https://github.com/source-foundry/Hack)

Visit [Nerd Fonts](https://nerdfonts.com/) They have a long list of good programming fonts (Hot Tip: 🔥)

### iTerm2

---

#### _Epic Better Console_

* Download and install [iTerm2](http://www.iterm2.com/)

* Configure oh-my-zsh with Cobalt2 theme but you can follow the same procedure for other themes

Paste on a terminal to install Oh-My-Zsh

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

Find more themes [here](https://github.com/robbyrussell/oh-my-zsh/wiki/External-themes)

### Homebrew

---

`Package Manager for OSX`

Find the documentation and manual install here
[Homebrew](http://brew.sh/).

* Install Homebrew on the terminal

```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

* One thing we need to do is tell the system to use programs installed by Homebrew (in `/usr/local/bin`) rather than the OS default if it exists. We do this by adding `/usr/local/bin` to your `$PATH` environment variable:

```bash
echo 'export PATH="/usr/local/bin:$PATH"' >> ~/.bash_profile
```

After this you can install applications like this

```bash
brew install visual-studio-code
brew install firefox sublime-text ...
```

### Git

---

#### _Configure Git and Aliases_

```bash
touch ~/.gitconfig
git config --global user.name "First Last"
git config --global user.email "Email"
git config --global credential.helper osxkeychain
```

Typical .gitconfig will look like this, be free to remove aliases

```bash
[user]
    name = First Last
    email = email@email.com
[github]
    user = username
[alias]
    a = add
    ca = commit -a
    cam = commit -am
    s = status
    pom = push origin master
    puom = pull origin master
    cob = checkout -b
[credential]
    helper = osxkeychain
```

### VSCode

---

#### _Best Code Editor_

```bash
brew install visual-studio-code
```

Open VSCode and type "shell command" and add to the PATH. Close VScode, restart Terminal , now you can open any project from the terminal using this

```bash
code \directory\to\open
```

#### Best Themes

0. [Sublime Material Theme](https://marketplace.visualstudio.com/items?itemName=jprestidge.theme-material-theme#review-details)
1. [Dracula]()
1. [Cobalt2]()

#### Best Plugins

0. [Seti Icons]()
1. [Auto-Open Markdown Preview]()
1. [Color Highlight]()
1. [ESLint]()
1. [Guides]()
1. [Import Cost]()
1. [npm Intellisense]()
1. [Prettier]()
1. [Sublime Babel]()
1. [Terminal]()

### Node

---

* Install Node

```bash
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.1/install.sh | bash
nvm install node
nvm use node
node -v
```

* Add to path

To do so, add this line to your `~/.path` file, before the `export PATH` line:

```bash
PATH=/usr/local/share/npm/bin:$PATH
```

#### _npm Usage_

npm Commands:

```bash
npm install <package>    # Install locally
npm install -g <package> # Install globally
npm install <package> --save # Save to a package.json file
npm list                # What's installed Locally
npm list -g             # what's installed Globally
npm outdated [-g]       # Find outdated packages
npm update [<package>]  # Upgrade particular package
npm uninstall <package> # Uninstall Packages
```

### Mongo

Follow this [guide](https://treehouse.github.io/installation-guides/mac/mongo-mac.html)

### Others

* Show hidden files, paste this on the command line

```bash
defaults write com.apple.finder AppleShowAllFiles YES
```

* Show path bar

```bash
defaults write com.apple.finder ShowPathbar -bool true
```

* Show status bar

```bash
defaults write com.apple.finder ShowStatusBar -bool true
```

### Heroku

---

#### _Heroku is a Platform-as-a-Service (PaaS) that simplifies deploying your apps online._

**Installation**

Assuming that you have an Heroku account (sign up if you don't), let's install the Heroku Client for the command-line using Homebrew.

```bash
brew install heroku/brew/heroku
npm install -g heroku-cli
```

The formula might not have the latest version of the Heroku Client, which is updated pretty often. Let's update it now:

```bash
heroku update
```

Don't be afraid to run heroku update every now and then to always have the most recent version.

**Setup**

Login to your Heroku account using your email and password:

```bash
heroku login
```

If this is a new account, and since you don't already have a public SSH key in your ~/.ssh directory, it will offer to create one for you. It will also upload the key to your Heroku account, which will allow you to deploy apps from this computer.

If it didn't offer create the SSH key for you (i.e. your Heroku account already has SSH keys associated with it), you can do so manually by running:

```bash
mkdir ~/.ssh
ssh-keygen -t rsa
```

Keep the default file name and skip the passphrase by just hitting Enter both times. Then, add the key to your Heroku account:

```bash
heroku keys:add
```

Usage

Once your keys are in place and you are authorized, you're ready to deploy apps. Heroku has a getting started [guide](https://devcenter.heroku.com/articles/python). Heroku uses Git to push code for deployment, so make sure your app is under Git version control.

**A cheat sheet for deployment**:

```bash
cd myapp/
heroku create myapp
git push heroku master
heroku ps
heroku logs -t
```

The Heroku Dev Center is where you will find more information.
