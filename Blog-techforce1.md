## My current code editor: Visual Code! or vscodium?

In the last few months i tried several different text editors, and at the moment i find myself starting up Visual Code most of the time. And...i think it's an awesome editor! With some tasks i still have to force myself to stay in the editor, like when using git or some other tasks.
There are a tons of plugins available to make my life as an Dev/Ops engineer so much better.

First I will cover my current setup of Visual code on Ubuntu 18.04 and after that a list of plugins.

### Setup visual code
Not much to say about setup, other than changing some default configuration settings.

So grab your preferred binary here: [https://code.visualstudio.com/](https://code.visualstudio.com/)

Sourcecode is available here: [https://github.com/microsoft/vscode](https://github.com/microsoft/vscode)

Since 4 april 2019 it is also released in the snapstore officially: Check it out here [https://snapcraft.io/code](https://snapcraft.io/code) 

Read and understand about data collection here and how to opt-out for most of it: [https://code.visualstudio.com/License/](https://code.visualstudio.com/License/)

And this point brings me to the title of this post. All this tracking/datacollecting stuff, why isn't there a version without any of this tracking/datacollecting stuff in it? Vscodium is here to the rescue. This is a compilation of vscode with everything related to data collection removed from the source: [https://www.fossmint.com/vscodium-clone-of-visual-studio-code-for-linux/](https://www.fossmint.com/vscodium-clone-of-visual-studio-code-for-linux/)
They also have builds for windows btw: [https://github.com/VSCodium/vscodium/releases](https://github.com/VSCodium/vscodium/releases). 
The only thing that is different is the icon, but everything else works just fine (also all the plugins etc).
Here is how to migrate your settings from vscode to vscodium: [https://vscodium.com/#migrate](https://vscodium.com/#migrate)

Well, installing it should be a next next finish kind of thing. On setup page for linux you can also make use of a deb repository: [https://code.visualstudio.com/docs/setup/setup-overview](https://code.visualstudio.com/docs/setup/setup-overview)

### Visual code updates
At the time of writing current version is 1.33.1 but every month there is an update for Visual code. You can check the release notes here: [https://code.visualstudio.com/updates](https://code.visualstudio.com/updates)
or watch video that is also released every month on their channel here: [https://www.youtube.com/channel/UCs5Y5_7XK8HLDX0SLNwkd3w](https://www.youtube.com/channel/UCs5Y5_7XK8HLDX0SLNwkd3w)

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
    "workbench.iconTheme": "vscode-icons",
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

### Here are some of the plugins which are quite handy (in a random order):

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

#### 3. [Vagrant](https://marketplace.visualstudio.com/items?itemName=bbenoist.vagrant)
Manage different aspects of your Vagrant boxes
![Vagrant](https://github.com/bbenoist/vscode-vagrant/raw/master/images/demo-single-machine.gif)

#### 4. [Vagrantfile Support](https://marketplace.visualstudio.com/items?itemName=marcostazi.VS-code-vagrantfile)
Syntax highlight your Vagrantfile

#### 5. [Ansible](https://marketplace.visualstudio.com/items?itemName=vscoss.vscode-ansible)
Run your Ansible playbook local, docker, in cloud. Code snippets and syntax highlighting. I really like this extension.
![Ansible](https://github.com/VSChina/vscode-ansible/raw/master/images/menu.png)

#### 6. [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python)
Snippets, syntax and much more!
![Python](https://raw.githubusercontent.com/microsoft/vscode-python/master/images/debugDemo.gif)

#### 7. [Go](https://marketplace.visualstudio.com/items?itemName=ms-vscode.Go)
Again, check the link for details. Snippets syntax and much more!

#### 8. [Code Runner](https://marketplace.visualstudio.com/items?itemName=formulahendry.code-runner)
Installing this plugin will enable you to quickly run your code/snippets.
![Code Runner](https://github.com/formulahendry/vscode-code-runner/raw/master/images/usage.gif)

#### 9. [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
![GitLens](https://raw.githubusercontent.com/eamodio/vscode-gitlens/master/images/docs/gitlens-preview.gif)

#### 10 [Test Kitchen](https://marketplace.visualstudio.com/items?itemName=jirkafajfr.vscode-kitchen)
Command palette for your kitchen tooling.
![Test Kitchen](https://github.com/jirkafajfr/vscode-kitchen/raw/master/assets/converge.gif)

#### 11 [Rest Client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client)
With this plugin it is possible to send kinds of http requests. So when you don't have postman installed, or want to to a quick request, you could do it with this plugin. 
![Rest Client](https://github.com/Huachao/vscode-restclient/raw/master/images/usage.gif)


#### 12 [AutoFileName](https://marketplace.visualstudio.com/items?itemName=JerryHong.autofilename)

Autocomplete your localfiles with this one
![AutoFileName](https://trello-attachments.s3.amazonaws.com/56c86fd76bf599f4fa62ee7f/1152x720/4b439177b0fb1c04af133aa733ba2a09/Untitled.gif)

#### 13 [Markdown Shortcuts](https://marketplace.visualstudio.com/items?itemName=mdickin.markdown-shortcuts)

Nice plugin for creating your Markdown documents
![Markdown Shortcuts](https://raw.githubusercontent.com/mdickin/vscode-markdown-shortcuts/master/media/demo/urls.gif)

#### 14 [Vscode icons](https://marketplace.visualstudio.com/items?itemName=vscode-icons-team.vscode-icons)

Just a bit of eyecandy, but also makes it more coherent.
![Vscode icons](https://raw.githubusercontent.com/vscode-icons/vscode-icons/master/images/screenshot.gif)

Let me know if i miss some super essential plugin, or a handy feature in vscode, thanks alot !

