# Installation Eggdrop Bot


Prerequisites
-

Make sure Tcl AND it’s dev packages are installed on your system. On Debian-based systems, this is done with:

	sudo apt-get install tcl tcl-dev

It is also STRONGLY recommended to have openssl installed, to enable SSL/TLS protection:

	sudo apt-get install openssl libssl-dev
------

Download eggdrop files
-

[Eggdrop 1.9.2 (tar.gz)](http://ftp.eggheads.org/pub/eggdrop/source/1.9/eggdrop-1.9.2.tar.gz) [2296Kb] – 2022-03-06



detailed explanation of these steps.

Download the latest stable Eggdrop release to your shell via FTP, or simply type 

	wget geteggdrop.com -O eggdrop-1.9.2.tar.gz
	
From the commadline of your shell, type: 

	tar zxvf eggdrop-1.9.2.tar.gz
	cd eggdrop-1.9.2
	./configure
   	make config
   	make
  	make install
   	cd ~/eggdrop

For a quick start, edit the eggdrop-basic.conf file. To take advantage of all Eggdrop’s features, we recommend using eggdrop.conf instead. It is also a good idea to rename the file to something easy to remember and specific to your bot, like botnick.conf.
Exeple:

   	./eggdrop -m <config file>

--------

# Configuration

You will need to edit the configuration file before you can start up your Eggdrop. You can find the example configuration file in the directory you extracted the Eggdrop source to, under the name ‘eggdrop.conf’. If you downloaded Eggdrop to your system, you can unzip the tarball (.tar.gz) file to its own directory using 7-Zip or a similar program, and view the example config file, botchk file, and all the documentation files locally. You can use Notepad to edit these files, although it’s sometimes desirable to use an editor that supports the Unix file format such as EditPlus. To edit the file once it is on your shell, a program such as ‘nano’ or ‘vim’ is recommended.



# Editing the config file

Eggdrop comes with two versions of the configuration file- eggdrop.conf and eggdrop-basic.conf. While it is recommended that users edit a copy of eggdrop.conf to take advantage of all the features Eggdrop has to offer, using eggdrop-basic.conf to start will be a quicker path for some. Still, it is recommended that you come back to the full config file at some point to see what you are missing.

It is first recommended to rename the sample config to something other than “eggdrop.conf”. Giving it the name of the bot’s nick (e.g. NiceBot.conf) is quite common. In the config file, you set up the IRC servers you want the bot to use and set Eggdrop’s options to suit your needs. Eggdrop has many options to configure, and editing the configuration file can take some time. I recommend you go over the entire config file to ensure the bot will be configured properly for your needs. All of the options in the config file have written explanations - be sure to read them carefully. Some of them can be a little bit vague, though.

To comment out a line (prevent the bot from reading that line), you can add a ‘#’ in front of a line. When you come to a line that you need to edit, one popular option is to comment out the original and add your new line right below it. This preserves the original line as an example. For example:

 Set the nick the bot uses on IRC, and on the botnet unless you specify a
 `copy(text: string, options: object): boolean` &mdash; tries to copy text to clipboard. Returns `true`
 
# Starting the Eggdrop

Phew! Now that you’ve compiled, installed, and configured Eggdrop, it’s time to start it up. Switch to the directory to which you installed the bot, cross your fingers, and type ./eggdrop -m <config> (where <config> is the name you gave to the config file). Eggdrop should start up, and the bot should appear on IRC within a few minutes. The -m option creates a new userfile for your bot, and is only needed the first time you start your Eggdrop. In future, you will only need to type ./eggdrop <config> to start the bot. Make sure you take the time to read what it tells you when you start it up!

Once your bot is on IRC, it’s important that you promptly introduce yourself to the bot. Msg it the ‘hello’ command you specified in the config file, e.g. /msg <botnick> hello. This will make you the bot’s owner. Once that’s done, you need to set a password using /msg <botnick> pass <password>. You can then DCC chat to the bot.

Now that your Eggdrop is on IRC and you’ve introduced yourself as owner, it’s time to learn how to use your Eggdrop!
	
	ffff
	
	
	
-------

# Automatically restarting an Eggdrop

A common question asked by users is, how can I configure Eggdrop to automatically restart should it die, such as after a reboot? To do that, we use the system’s crontab daemon to run a script (called botchk) every ten minutes that checks if the eggdrop is running. If the eggdrop is not running, the script will restart the bot, with an optional email sent to the user informing them of the action. To make this process as simple as possible, we have included a script that can automatically configure your crontab and botchk scripts for you. To set up your crontab/botchk combo
	
Enter the directory you installed your Eggdrop to. Most commonly, this is ~/eggdrop (also known as /home/<username>/eggdrop).
Just humor us- run `./scripts/autobotchk` without any arguments and read the options available to you. They’re listed there for a reason!
-
	
If you don’t want to customize anything via the options listed in #2, you can start the script simply by running:
`./scripts/autobotchk yourEggdropConfigNameHere.conf`

Review the output of the script, and verify your new crontab entry by typing:

	crontab -l
	


By default, it should create an entry that looks similar to:

`0,10,20,30,40,50 * * * * /home/user/bot/scripts/YourEggdrop.botchk 2>&1`

This will run the generated botchk script every ten minutes and restart your Eggdrop if it is not running during the check. Also note that if you run autobotchk from the scripts directory, you’ll have to manually specify your config file location with the -dir option. To remove a crontab entry, use crontab -e to open the crontab file in your system’s default editor and remove the crontab line.




---------
# FINISH HERE



-------------------
custom Qtile for ArchLinux

After instal Qtile:

	sudo pacman -S gdm kitty ----
	
	

installing repos for BlackArch 

	mkdir blackarch
	cd !$
	curl -O https://blackarch.org/strap.sh
	chmod +x strap.sh
	sudo su
	./strap.sh
	
	pacman -Sy


Install Qtile and dependencies:

	sudo pacman -S qtile pacman-contrib
	sudo pacman -S noto-fonts-emoji noto-fonts 

In case of YAY:

	yay -S nerd-fonts-ubuntu-mono
	
	
or in case PARU:
instalation PARU

create repo directory

	mkdir repos
	git clone https://aur.archlinux.org/paru-bin.git
	cd paru-bin
	makepkg -si

after finish installeting PARU

	paru -S nerd-fonts-ubuntu-mono
	
next:

	pip install psutil
	
if missed this:

	sudo pacman -S python-pip


Clone this repository and copy my configs:

	git clone https://github.com/antoniosarosi/dotfiles.git
	cp -r dotfiles/.config/qtile ~/.config







--------------------------------------------------


......

sudo pacman -S qtile pacman-contrib

yay or paru -S nerd-fonts-ubuntu-mono



		if yay then: pip install psutil


<clipboard-copy> element
	

# Copy to clipboard [![Build Status](https://travis-ci.org/sudodoki/copy-to-clipboard.svg?branch=master)](https://travis-ci.org/sudodoki/copy-to-clipboard)

Simple module exposing `copy` function that will try to use [execCommand](https://developer.mozilla.org/en-US/docs/Web/API/Document/execCommand#) with fallback to IE-specific `clipboardData` interface and finally, resort to usual `prompt` with proper text content and message.

# Example

```js
import copy from 'copy-to-clipboard';

copy('Text');

// Copy with options
copy('Text', {
  debug: true,
  message: 'Press #{key} to copy',
});
```

# API

`copy(text: string, options: object): boolean` &mdash; tries to copy text to clipboard. Returns `true` if no additional keystrokes were required from user (so, `execCommand`, IE's `clipboardData` worked) or `false`.

|Value |Default |Notes|
|------|--------|-----|
|options.debug  |false| `Boolean`. Optional. Enable output to console. |
|options.message|Copy to clipboard: `#{key}`, Enter| `String`. Optional. Prompt message. `*` |
|options.format|"text/html"| `String`. Optional. Set the MIME type of what you want to copy as. Use `text/html` to copy as HTML, `text/plain` to avoid inherited styles showing when pasted into rich text editor. |
|options.onCopy|null| `function onCopy(clipboardData: object): void`. Optional. Receives the clipboardData element for adding custom behavior such as additional formats |

`*` all occurrences of `#{key}` are replaced with `⌘+C` for macOS/iOS users, and `Ctrl+C` otherwise.

# [Browser support](http://caniuse.com/#feat=document-execcommand)

Works everywhere where `prompt`* is available. Works best (i.e. without additional keystrokes) in Chrome, FF, Safari 10+, and, supposedly, IE/Edge.

Note: **does not work on some older iOS devices.**  
`*` – even though **Safari 8** has `prompt`, you cannot specify prefilled content for prompt modal – thus it **doesn't work** as expected.

# Installation

+ Can be used as npm package and then leveraged using commonjs bundler/loader:
```
npm i --save copy-to-clipboard
```
+ Can be utilized using [wzrd.in](https://wzrd.in/). Add following script to your page:
```html
<script src="https://wzrd.in/standalone/copy-to-clipboard@latest" async></script>
```
You will have `window.copyToClipboard` exposed for you to use.

# UI components based on this package:
+ [react-copy-to-clipboard](https://github.com/nkbt/react-copy-to-clipboard)
+ [copy-button](https://github.com/sudodoki/copy-button)

# See also:
+ [clipboard-copy](https://github.com/feross/clipboard-copy) by [@feross](https://github.com/feross)
+ [MDN](https://developer.mozilla.org/en-US/docs/Web/API/Document/execCommand#Browser_Compatibility)
+ [April 2015 update on Cut and Copy Commands](http://updates.html5rocks.com/2015/04/cut-and-copy-commands)

# Running Tests
This project has some automated tests, that will run using [nightwatch](nightwatchjs.org) on top of [selenium](http://www.seleniumhq.org/).

```
npm i
npm test
```
# Typescript
This library has built-in Typescript definitions.

```
import * as copy from 'copy-to-clipboard';
```
