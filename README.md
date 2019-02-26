## My current code editor: Visual Code!

In the last few months i tried several different text editors, and at the moment i find myself starting up Visual Code most of the time. And...i think it's an awesome editor!
There are a tons of plugins available to make my life as an Dev/Ops engineer so much better.

First I will cover my current setup of Visual code on Ubuntu 18.04 and after that a list of plugins.

### Setup visual code
Not much to say about setup, other than changing some default configuration settings.

So grab your preferred binary here: [https://code.visualstudio.com/](https://code.visualstudio.com/)

Sourcecode is available here: [https://github.com/microsoft/vscode](https://github.com/microsoft/vscode)

Read and understand about data collection here and how to opt-out for most of it: [https://code.visualstudio.com/License/](https://code.visualstudio.com/License/)

Well, installing it should be a next next finish kind of thing. On setup page for linux you can also make use of a deb repository: [https://code.visualstudio.com/docs/setup/setup-overview](https://code.visualstudio.com/docs/setup/setup-overview)

### Keybindings!
Chances are that you find yourself using another editor, and you are used to keybindings of that editor.
Fortunately there are loads of keymappings/keybinding plugins available to make the transition easier to Visual Code.

* [Atom Keymap](https://marketplace.visualstudio.com/items?itemName=ms-vscode.atom-keybindings)
* [Visual Studio Keymap ](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vs-keybindings)
* [Notepad++ keymap](https://marketplace.visualstudio.com/items?itemName=ms-vscode.notepadplusplus-keybindings)
* [Vim Keymap](https://marketplace.visualstudio.com/items?itemName=GiuseppeCesarano.vim-keymap)
* [Sublime Text Keymap and Settings Importer](https://marketplace.visualstudio.com/items?itemName=ms-vscode.sublime-keybindings)
* [IntelliJ IDEA Keybindings](https://marketplace.visualstudio.com/items?itemName=k--kato.intellij-idea-keybindings)


### Git font issues in ubuntu 18.04:
Every year i switch between a rpm based distro and a debian based one. Right now i have a debian based distro for my xps 9570 (shoutout to the 9570 respin repo: [https://github.com/JackHack96/dell-xps-9570-ubuntu-respin](https://github.com/JackHack96/dell-xps-9570-ubuntu-respin)). I think the setup will not differ much between mac/and other linux distro's but this setup is based on Ubuntu 18.04 with the zsh shell and [ohmyzsh](https://ohmyz.sh/) installed and the powerline9k theme selected.

So Visual code (or code) has a built in terminal but my lettertype doesn’t contain any of the git symbols.
First we're gonna fix exactly this.
Also very nice, all of your (non-default/personal) settings are in a json file. Open your settings with the following shortcut:
```
ctrl+,
```


### My personal settings:
```json
{
    "telemetry.enableTelemetry": false,
    "terminal.integrated.fontFamily": "MesloLGL Nerd Font",
    "terminal.integrated.fontSize": 14,
    "extensions.autoUpdate": true,
    "window.zoomLevel": 0
}
```

To fix my VisualCode terminal i needed to download an extra font (so ohmyzsh/zsh and powerline9k theme is working correctly)

```
mkdir ~/.fonts/
wget https://github.com/ryanoasis/nerd-fonts/releases/download/v2.0.0/Meslo.zip
cd .fonts
unzip Meslo.zip
rm Meslo.zip
```

### Starting code
There are handy commandline switches you could use to startup code with.
```
Options
  -d --diff <file> <file>           Compare two files with each other.
  -a --add <folder>                 Add folder(s) to the last active window.
  -g --goto <file:line[:character]> Open a file at the path on the specified line and character position.
  -n --new-window                   Force to open a new window.
  -r --reuse-window                 Force to open a file or folder in an already opened window.
  -w --wait                         Wait for the files to be closed before returning.
  --locale <locale>                 The locale to use (e.g. en-US or zh-TW).
  --user-data-dir <dir>             Specifies the directory that user data is kept in. Can be used to open multiple distinct instances of Code.
  -v --version                      Print version.
  -h --help                         Print usage.
  --folder-uri <uri>                Opens a window with given folder uri(s)
  --file-uri <uri>                  Opens a window with given file uri(s)
```


### Here are my top 10 used plugins (in random order):

#### 1. [Docker explorer](https://marketplace.visualstudio.com/items?itemName=formulahendry.docker-explorer)

**From the pluginpage, please pay attention to:**

By default, anonymous telemetry data collection is turned on to understand user behavior to improve this extension. To disable it, update the settings.json as below:
```
{
    "docker-explorer.enableTelemetry": false
}
```



#### 2. [Azure account](https://marketplace.visualstudio.com/items?itemName=ms-vscode.azure-account)

This one is great for managing different aspects of your azure account. Uploading files to cloud shell and much more!

#### 3. [Sort lines](https://marketplace.visualstudio.com/items?itemName=Tyriar.sort-lines)

Sort stuff with different options

#### 4. [AutoFileName](https://marketplace.visualstudio.com/items?itemName=JerryHong.autofilename)

Auto complete your local files.

#### 5. [Vagrant](https://marketplace.visualstudio.com/items?itemName=bbenoist.vagrant)

Manage different aspects of your Vagrant boxes

#### 6. [Vagrantfile Support](https://marketplace.visualstudio.com/items?itemName=marcostazi.VS-code-vagrantfile)

Syntax highlight your Vagrantfile

#### 7. [Ansible](https://marketplace.visualstudio.com/items?itemName=vscoss.vscode-ansible)

Run your Ansible playbook local, docker, in cloud and other stuff.

#### 8. [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python)

Snippets, syntax and much more!

#### 9. [Go](https://marketplace.visualstudio.com/items?itemName=ms-vscode.Go)

Again, check the link for details. Snippets syntax and much more!

#### 10. [Code Runner](https://marketplace.visualstudio.com/items?itemName=formulahendry.code-runner)

#### 11. [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
![GitLens](https://raw.githubusercontent.com/eamodio/vscode-gitlens/master/images/docs/gitlens-preview.gif)

#### 12 [Test Kitchen](https://marketplace.visualstudio.com/items?itemName=jirkafajfr.vscode-kitchen)
![Test Kitchen](https://github.com/jirkafajfr/vscode-kitchen/raw/master/assets/converge.gif)
