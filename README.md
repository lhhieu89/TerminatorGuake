# TerminatorGuake
Make Terminator Terminal Act Like Guake Terminal

### Install Terminator
```sh
sudo add-apt-repository ppa:gnome-terminator/ppa
sudo apt-get update
sudo apt-get install terminator
```
### Config Terminator
Backup Termincator config:
```sh
cp ~/.config/terminator/config ~/.config/terminator/config.bk
```
Add the following text to `~/.config/terminator/config`
```config
[global_config]
  enabled_plugins = LaunchpadCodeURLHandler, APTURLHandler, LaunchpadBugURLHandler
  always_on_top = False
  tab_position = top
  sticky = True
[keybindings]
  hide_window = F3
[profiles]
  [[default]]
    background_darkness = 0.75
    background_type = transparent
    foreground_color = "#ffffff"
[layouts]
  [[default]]
    [[[child0]]]
      position = 0:24
      type = Window
      order = 0
      parent = ""
      size = 1679, 500
    [[[child1]]]
      position = 839
      type = HPaned
      order = 0
      parent = child0
    [[[terminal3]]]
      profile = default
      type = Terminal
      order = 1
      parent = child1
    [[[terminal2]]]
      profile = default
      type = Terminal
      order = 0
      parent = child1
  [[original]]
    [[[child1]]]
      type = Terminal
      parent = window0
      profile = default
    [[[window0]]]
      type = Window
      order = 0
      parent = ""
[plugins]
```
This will configure terminator to accept the F3 button as a hide/show command wherever you are and will initially create a session with two terminals when you start terminator
