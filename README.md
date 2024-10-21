# bookmarks

This is a collection of bookmarks that I have found useful. I have organized them by category.

## [Oh My ZSH!](https://ohmyz.sh/)

**tags**: "zsh", "shell", "terminal", "oh-my-zsh"

**description**: Unleash your terminal like never before.
Oh My Zsh is a delightful, open source, community-driven framework for managing your Zsh configuration. It comes bundled with thousands of helpful functions, helpers, plugins, themes, and a few things that make you shout...

**installation**:

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

**plugins**:

- [Oh my ZSH with zsh-autosuggestions zsh-syntax-highlighting zsh-fast-syntax-highlighting and zsh-autocomplete.md](https://gist.github.com/n1snt/454b879b8f0b7995740ae04c5fb5b7df)

## [keyd](https://github.com/rvaiya/keyd?tab=readme-ov-file)

**description**:  A key remapping daemon for linux

**tags**: "keyd", "key", "remapping", "daemon", "linux"

**installation**:

```bash
git clone https://github.com/rvaiya/keyd
cd keyd
make && sudo make install
sudo systemctl enable keyd && sudo systemctl start keyd
sudo nano /etc/keyd/default.conf
```

Put the following in /etc/keyd/default.conf:

```conf
[ids]

*

[main]

# Maps capslock to escape when pressed and control when held.
capslock = overload(control, esc)

# Remaps the escape key to capslock
esc = capslock
```

Key names can be obtained by using the keyd monitor command. Note that while keyd is running, the output of this command will correspond to keyd's output. The original input events can be seen by first stopping keyd and then running the command. See the man page for more details.

Run sudo keyd reload to reload the config set.

See the man page (man keyd) for a more comprehensive description.

Config errors will appear in the log output and can be accessed in the usual way using your system's service manager (e.g sudo journalctl -eu keyd).

_Note_: It is possible to render your machine unusable with a bad config file. Should you find yourself in this position, the special key sequence backspace+escape+enter should cause keyd to terminate.

Some mice (e.g the Logitech MX Master) are capable of emitting keys and are consequently matched by the wildcard id. It may be necessary to explicitly blacklist these.

## Vim motion

**nav**:

`h` --- Left
`j` --- Down
`k` --- Up
`l` --- Right
`gg` --- Go to the start of the page
`G` --- Go to the end of the page
`$` --- Go to the end of the line
`^`|`0` --- Go to the start of the line
`{` --- Go to the new line before a block of paragraph
`}` --- Go to the new line after a block of paragraph
`w` --- Move forword by word
`W` --- Move forword by word seperated by whitespace
`b` --- Move backword by word
`B` --- Move backword by word seperated by whitespace

`u` --- undo
`ctrl`+`r` --- redo

`i` --- Insert mode, before cursor
`I` --- Insert mode, at the start of the line of the cursor
`a` --- Insert mode, after cursor _(think of appending)_
`A` --- Insert mode, at the end of the line of the cursor
`o` --- Insert mode, making a new line after the line that has the cursor
`O` --- Insert mode, making a new line after the line that has the cursor

`dd` --- delete line
`di`+**specific character**_(like `{` or `(`)_  --- delete what's inside the **apecific character** currently in _(think of delete inner)_
`dit` --- deletes what's between:W
 `>` and `<`
`dat` --- deletes the xml/html like tag with it's content 
`D`|`d}` --- Deletes the rest of the line after the cursor
`df`+character --- Delete until **after** the character
`dt`+character --- Delete until **before** the character
`d`+**nav** commands ---

Note: `d` and `c` will delete but the differnce is that `c` will inter the **Insert Mode** _(think about deleting vs changing)_

`yy`|`Y` -- copy line

`p` --- pasting what's yanked or in the buffer _(like for example when deleting)_ after the cursor
`P` --- pasting what's yanked or in the buffer _(like for example when deleting)_ before the cursor


In Visiual mode _(entered by pressing `v` on normal/command mode)_
`y` --- copy selection _(yanking/copyng)_
`d` --- delete selction

`r` --- replace the charachter without going to the insert mode

`f`+character --- Search forward for the character
`F`+character --- Search backward for the character

`/`+search term --- To navigate use `n` backward and  `N` to navigate forward
`#` --- will search the **word** the cursor on backward
`*` --- will search the **word** the cursor on forward
