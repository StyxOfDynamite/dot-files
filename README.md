### .files

![gif](https://gitlab.hq.jadu.net/luke.storer/dotfiles/blob/master/dotfiles.mov.gif "Demo")



The dotfiles in this project add some pretty cool functionality / shortcuts to your Mac terminal.
Some are definately more useful than others.

Loading the .files is handled when the terminal starts using `.bash_profile`

	# Load the shell dotfiles, and then some:
	for file in ~/.{path,bash_prompt,exports,aliases,functions}; do
		[ -r "$file" ] && [ -f "$file" ] && source "$file"
	done
	unset file

## installation
as you might already have some .files configured in your `~` you can just append these to your exsiting .files using `cat`
e.g.

	cat .newfile >> .existingfile

## .path

as you might have guessed this .file handles setting up your custom path, mine just adds `~/bin` which
is where I happen to symlink any custom scripts to

## .bash_prompt

this is my custom bash prompt, it has a few tweaks such as:

+ no username or host if they are the default.
+ its funky colors
+ git info on the path

## .exports
this file handles setting some defaults up:

+ nano as the text editor
+ larger bash history
+ ignore some commands in history
+ highlight section titles in manual pages
+ don’t clear the screen after quitting a manual page
+ always enable colored `grep` output

## .aliases
loads of aliases, some pretty helpful, some less so maybe:

+ svn up without externals
+ easier navigation
+ shortcuts
+ lists and stuff in color
+ stopwatch
+ enhanced lookup
+ flush dns
+ empty trash
+ show/hide hidden files in Finder
+ show/hide all desktop icons (useful when presenting)
+ urlencode strings (bit flakey)
+ enable / disable spotlight
+ lock screen

## .functions
some handy functions, some less handy ones:

+ create a new directory and enter it
+ create a .tar.gz archive, using `zopfli`, `pigz` or `gzip` for compression
+ determine size of a file or total size of a directory
+ use Git’s colored diff when available
+ create a data URL from a file
+ create a git.io short URL (for github urls)
+ start an HTTP server from a directory, optionally specifying the port
+ start a php webserver in the current directory
+ escape UTF-8 characters into their 3-byte format
+ add reminder to Reminders.app (OS X 10.8)
+ `s` with no arguments opens the current directory in Sublime Text, otherwise opens the given location
+ `tre` is a shorthand for `tree` with hidden files and color enabled, ignoring the `.git` directory, listing directories first. The output gets piped into `less` with options to preserve color and line numbers, unless the output is small enough for one screen.
+ animated gifs from any video from alex sexton gist.github.com/SlexAxton/4989674
+ pretty print JSON

## .bashrc
sometimes Terminal.app launches with this file instead of bash_profile, skipping the .files loader so if this happens we call the .bash_profile