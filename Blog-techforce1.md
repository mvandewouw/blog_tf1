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

More on keybindings [here](https://code.visualstudio.com/docs/getstarted/keybindings)


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
    "telemetry.enableCrashReporter": false,
    "terminal.integrated.fontFamily": "MesloLGL Nerd Font",
    "terminal.integrated.fontSize": 14,
    "docker-explorer.enableTelemetry": false,
    "extensions.autoUpdate": true,
    "gitlens.advanced.messages": {
       "suppressShowKeyBindingsNotice": true
    },
    "foodcritic.enable": true,
    "breadcrumbs.enabled": true
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

The 3 options i use the most are the -n -r or -g flag.

### Here are my top 10 used plugins (in random order):

#### 1. [Docker explorer](https://marketplace.visualstudio.com/items?itemName=formulahendry.docker-explorer)
This is a great plugin for managing different aspects of your docker platform. 

**From the pluginpage, please pay attention to:**

By default, anonymous telemetry data collection is turned on to understand user behavior to improve this extension. To disable it, update the settings.json as below:
```
{
    "docker-explorer.enableTelemetry": false
}
```

![Docker Explorer](https://github.com/formulahendry/vscode-docker-explorer/raw/master/images/explorer.png)

#### 2. [Azure Storage](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurestorage)

Quickly uploading a static site to your azure blob is very easy with this plugin.
![Azure Storage](https://github.com/Microsoft/vscode-azurestorage/raw/master/resources/SignIn.gif)

#### 3. [AutoFileName](https://marketplace.visualstudio.com/items?itemName=JerryHong.autofilename)

Auto complete your local files.

#### 4. [Vagrant](https://marketplace.visualstudio.com/items?itemName=bbenoist.vagrant)

Manage different aspects of your Vagrant boxes

#### 5. [Vagrantfile Support](https://marketplace.visualstudio.com/items?itemName=marcostazi.VS-code-vagrantfile)

Syntax highlight your Vagrantfile

#### 6. [Ansible](https://marketplace.visualstudio.com/items?itemName=vscoss.vscode-ansible)

Run your Ansible playbook local, docker, in cloud. Code snippets and syntax highlighting. I really like this extension.

#### 7. [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python)

Snippets, syntax and much more!

#### 8. [Go](https://marketplace.visualstudio.com/items?itemName=ms-vscode.Go)

Again, check the link for details. Snippets syntax and much more!

#### 9. [Code Runner](https://marketplace.visualstudio.com/items?itemName=formulahendry.code-runner)
Installing this plugin will enable you to quickly run your code/snippets.
![Code Runner](https://github.com/formulahendry/vscode-code-runner/raw/master/images/usage.gif)

#### 10. [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
![GitLens](https://raw.githubusercontent.com/eamodio/vscode-gitlens/master/images/docs/gitlens-preview.gif)

#### 11 [Test Kitchen](https://marketplace.visualstudio.com/items?itemName=jirkafajfr.vscode-kitchen)
![Test Kitchen](https://github.com/jirkafajfr/vscode-kitchen/raw/master/assets/converge.gif)

#### 12 [Rest Client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client)
With this plugin it is possible to send kinds of http requests. So when you don't have postman installed, or want to to a quick request, you could do it with this plugin. 
![Rest Client](https://github.com/Huachao/vscode-restclient/raw/master/images/usage.gif)


#### 13 [AutoFileName](https://marketplace.visualstudio.com/items?itemName=JerryHong.autofilename)
![AutoFileName](https://trello-attachments.s3.amazonaws.com/56c86fd76bf599f4fa62ee7f/1152x720/4b439177b0fb1c04af133aa733ba2a09/Untitled.gif)

#### 14 [Markdown Shortcuts](https://marketplace.visualstudio.com/items?itemName=mdickin.markdown-shortcuts)

Nice plugin for creating your Markdown documents
![Markdown Shortcuts](https://raw.githubusercontent.com/mdickin/vscode-markdown-shortcuts/master/media/demo/urls.gif)