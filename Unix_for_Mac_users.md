Unix for mac OS X users
===

###Intro to Unix

#### Brief History of Unix

Unix is an operating system developed by AT&T emplyees at Bell Labs between 1969 and 1971.
It all started by designing a mainframe called, Multex (Multiplexed Information and Computing Service). Unfortunalty, Multex became too expensive to operate, but the engineers loved the projects goals. As a result, they created Unics (Uniplexed Information and Computed Service); later renamed Unix.

In 1972, Unix was rewritten in the C programming language. 

* C was developed for the unic OS. 
* C allowed Unix to be portable.

Unix spread outside AT&T in 1975. Anyone could request a copy of Unix from AT&T, and AT&T would send them their liscenses and source code.

Since, 1975 branches and improvements were released.

* Open source: BSD (Berkeley Software Distribution), Linux
* Closed Source: Solaris (Sun/Oracle), AIX (IBM), HP/UX (Hewlett-Packard)
* Mixed source: Mac OS X (Apple)
 
Today, Unix means a Unix-like system, becasue of all improvements. Mobile deivces run on Unix as well.

Mac OS X runs on Darwin, which is a combination of, BSD Unix + NeXTSTEP + Apple code. This allows you to interact with Unix directly through the  terminal. 
 
Unix is used directly for a couple of reasons. It allows for very data intensive task. When working with data, non-data elements can get in the way. In conclusion, you give up convinience for control.

#### The Terminal Application

This is the way to interact with Unix. It comes preinstalled with Unix. Access it using:

* Shift + command + u: Open the Utilities folder 

#### Logging and using the command prompt

When you open the terminal a new session starts as a user. 

##### Terminal shortcuts

* up and down arrow: Review previous commands
* control + a: Move cursor to start of line
* control + e: move cursor to end of line
* tab: try to complete the comand or filename
* tab + tab: When tab does not complete, show  list of possible matches
* command + ~: Cycle between Terminal windows
* command + or -: changes the size of terminal 
	
* command + k clear scroll back, a.k.a. clear screen
	
* command + n opens new window

#### Command Structure

This is the order of our structure:

	Command		options		arguments

**command** -always a single word

**options** -modify the behavior of the command. These are optional.

**arguments** - the thing that we want the command to use when doing whatever that command does.

	echo 'Hello World'
 
	echo -n 'Hello World'

Use a semi-colon to break up commands. e.g.

	echo 'hello'; 'world'


#### Kernel and shells

**Kernel**

* Core of the OS
* Allocates time and memory to programs
* Mac OS X uses the Mach kernel

**Shell**

* Outer layer of OS
* Interacts with user
* Sends requests to kernel 
* Mac OS X uses the bash shell, but includes other choices

Other Popular Shells

* sh: Thompson Shell (1971)
* sh: Bourne Shell (1977)
	* replaced the Thompson Shell
* csh: C Shell (1979)
* tcsh: Tabbed C Shell (1979)
* ksh: Korn Shell (1982)
* bash: Bourne-Again Shell (1987)
* zsh: Z Shell (1990)

The differences between these shells is miniscule. Different shell offer different features. However, these differences are important for high end users who do a lot of high shell scripting. For now, stick to the bash shell to learn.

Find out what shell you are in upon log in e.g.

	echo $SHELL

Find out what shell you are currently woking in e.g.

	echo $0

Change between shells

	type name of SHELL

#### Unix manual pages

Invaluble resource for helping you figure out what you want to do when working in Unix. e.g.

	man (command)

* view next page: press spacebar
* view previous page: press 'b' key
* leave man: press 'q' key
	
Another method is to use, `apropos`. This searchs the database for strings containing short descriptions of system commands for key words and displays the results on the standard output.

	apropos (beginging of command)

### Filesystem Basics

#### The working directory

Working diectory is the current directory. Find out which directory you are in e.g.

* pwd
	* Present working directory

#### Listing files and directories

	ls
		Lists files in present working directory.
	ls -l
		Lists files in vertical format.
	ls -la
		Lists files vertically. Also lists current directory, parent directories, 			
		and invisible config directories.
	ls -lah
		Same as 'ls -la', but includes the size of the file in human readable format.

	*Note*: lines that start with a '-' are files. Lines that start with a 'd' are directories.

#### Moving around the filesystem

	cd (directory name)
		change between directories
	cd -
		go back to previous diectory
	cd (directory name)/(directory)
		navigate to multiple directories at once
	cd ~
		navigate to user directory
	cd ..
		navigate to parent directory
#### Filesystem orginization

![Filesystem Organization](/Users/macuser/Desktop/Screen Shot 2015-05-26 at 12.00.46 PM.png)

![Mac-only files and directories](/Users/macuser/Desktop/Screen Shot 2015-05-26 at 12.03.49 PM.png)

### Working with Files and Directories

#### Naming files

* Maximum of 255 characters
* Avoid / \ * & % $ | ^ ~ < > and most other symbols
	* These have special meanings in Unix, therefore it may confuse your file name for a command.
* Use A-Z, a-z, 0-9, period, underscore, hyphen
	* Don't use period or hyphen as first character
* Typically stick to lowercase, since Unix is case sensitive
* Underscores are better than spaces
	* Use quotes around names with spaces
* Use file endings (.txt, .png, .html, etc.) not required but helpful
	* Differentiates files from commands and directories


#### Creating Files

	touch new_file.txt

#### Unix text editors

**ed** (Edit text)

* Earliest Unix editor, not user friendly

**vi** (visual editing mode), **vim** (vi improved)

* Modal, fingers rarely leave keyboard home row

**GNU Emacs** (editor macros)

* Macros to automate work, swiss army knife

**pico** (pine composer), **nano**(1000x larger than pico)

* Basic features, easy to use
* http://www.nano-editor.org
	* Nano user manual

#### Reading files

**cat**

 * Concatenate
 
Drawback of using 'cat' is, all the files are displayed at once. This requires a lot of scrolling, especially for longer files.

**more**

* Paginated output

Outputs one page of text then waits for you to press spacebar. The drawback of this is, you can only go forward. If you want to go back, you have to enter the command again.

**less**

* Backward scrolling
* Better memory use
* less > more

Press 'g' key

* Go to start

shift + 'g'

* go to end

#### Reading portions of files

**head**

* Display lines from beginning of a file

**tail**

* Display lines from end of a file

**tail -f**

* "Follow" the tail of a file

**exit**

* ctrl + c



#### Creating directories

	mkdir testdir

Create a directory within a directory e.g.

	mkdir testdir/test1

Create a directory within a directory, within another directory e.g.

	mkdir -p testdir/test1/test2

#### Moving and renaming files and directories

Moving files:

	mv newfile.txt testdir

Move to parent directory of **testdir**:

	mv newfile.txt ..

Renaming files:

	mv newfile.txt newfile1.txt

**mv options**

| Option | Description|
| ------ | ---------- |
| -n     |No Overwriting|
| -f     |Force overwriting|
| -i     |Interactice overwriting, provides options|
| -v     |verbose|

*Note*: -f is the default command when moving files

#### Copying files and directories

	cp new_file.txt

#### Deleting files and directories

Files e.g.

	rm newfile.txt

Directories

	rm dir test_dir

* only removes empty directories

	rm -rf test_dir

* remove directories recursively

#### Finder aliases in Unix

Alias files are large files that are useful to the finder. In the finder click on the file and press `command + L`, to make an alias

Instead of using aliases we are going to use links.

#### Hard links

Hardlinks are, references to a a file in the filesystem. They don't break if the file is moved. However, unlike the alias, if the file is deleted the the hard link does not break.

	ln filetolink hardlink

**How is this different from copying???**

#### Symbolic links

Also known as "sym link"

	ln -s filetolink symlink

Unlike hard links, sym links reference a file path or a directory path. Unfortunately, they break if the file is moved or deleted.

#### Searching for files and directories

	find path expression e.g.

	find ~/Documents -name "newimage.jpg"

**Wildcard Characters**

|Wildcard|Meaning|
|--------|-------|
|*| zero or more characters|
|[ ]|any character in the brackets|
|?|any one character|


### Ownership and Permissions

#### Who am I?

Navigate to home directory:

`cd ~`

#### Unix Groups

A group is a set of users and it is useful for associating a group of user to a file. Find out what groups you have access to by using the `groups` command.

#### File and directory ownership

Changing file ownership:

	chown macuser:staff newfile.txt

#### File and directory permissions

View permissions:

`ls -la`

The first column of this command shows what rights and permissions are granted.

![Permissions](/Users/macuser/Desktop/Screen Shot 2015-05-27 at 10.51.28 PM.png)


**Alpha Notation**

||__user__|__group__|__other__|
|----|------|----|
|read (r)|yes|yes|yes|
|write (w)|yes|yes|no|
|execute (x)|yes|no|no|
||rwx|rw-|r--|

#### Setting permissions using alpha notation

Changing permissions:

	chmod mode filename

Add write permission to user and group:

	chmod ug+w filename

Take away write permission from other: 

	chmod o-w filename

user= u

group= g

other= o


#### Setting permissions using octal notation

**Alpha to Octal Conversion**

r=4

w=2

x=1

instead of:

	chmod rwx filename

use:

	chmod 777 filename

* this gives the user, group and other the permisson to read write and execute.

	chmod 764 filename

* user can read, write and execute; the group can read and write; other can read.

#### The root user

* Superuser account that can do **anything** on the system
* Root user is disabled by default in Mac OS X
* Why talk about it?
	* Important Unix concept
	* May read or hear references to "root"
	* Remote Unix servers usually have the root user enabled
	* Important when dicussing sudo


#### Sudo and sudoers

`Sudo` stands for, substitute user and do.

A command that runs other commands through root.

Substitute root for another user:

	sudo -u guest whoami

* only admins can run sudo command

### Commands and Programs

#### Command basics

Command options: -v, --version, --help

Exit: q, x, ctrl+q, ctrl+x, or ESC

Force quit: Ctrl+c

* Closing the terminal window is another option. However, the process will keep running.

* whereis
	* locate programs
* whatis
	* search the whatis database for complete words
* which
	* prints the full path of a command

Semicolons between commands


#### The PATH variable

The PATH variable is an environment variable specifying a set of directories where executable programs are located.

`echo $PATH`

* Displays the current value of your PATH

`PATH=(new PATH)`

* Will change your PATH variable, only for that session


#### System information commands

`date`

* Displays current date

`uptime`

* Lenght of time that terminal has been turned on

`users`

* Displays which user is logged in

`uname`

* Displays name of operating system

`uname -mnrsvp` **OR** `uname -ap`

* Displays detailed information about the operating system


#### Disk information commands

`df -h`

* Stands for, disk freespace

`df -H`

* Uses base ten to display disk freespace
 
`du ~/(testdir)/`

* Displays disk usage space in given directory

#### Viewing processes

`ps`

* Displays process status

`ps -a`

* Displays processes owned by other users

`ps aux`

* Displays all processes, the user that owns the processes, and any background processes

#### Monitoring processes

	top

* Displays updated information about processes
* Press 'q' to exit
* Press '?' for help


#### Stopping processes

	ctrl + c

* Stops a process

	kill (process ID)

* Process ID can be found in the second column following the `ps command`

	kill -9 (process ID)

* Forcibly kills the process, because some processes cannot be killed without force

#### Text file helpers

	wc filename.txt

* word count
* first number is the number of lines in the file
* second number is the number of words int he file
* third number is the number of characters in the file

	sort filename.txt

* sort lines of text file
* capital letters and lowercase letters are treated differently.
	* `-r` reverses the sort order
	* `-u` removes duplicates
	
	uniq filename

* filter in/out repeated lines
	* `-d` outputs repeated lines
	* `-u` outputs lines that are not repeated


#### Utility programs

	cal/ ncal
 
* calender
	* `-y` displays a calender for a specified year
	* `ncal` offers an alternative layout
	
	bc

* An arbitrary precision calculator language 
	* `quit` to exit program

	expr

* expression evaluator

	units

* unit conversion
	* `ctrl + c` will abort program


#### Using the command history

Unix stores its history of commands in file, .bash_history. View this using `cat`.

Commands are recorded once we quit the terminal window. In order to view a full list of commands use `history`.

**Command History Shortcuts**

|Command|Description|
|-----|-----|
|!4|References history command #4|
|!-3|References command which was 3 commands-back|
|!cat|References most recent command beginning with `cat`|
|!!|References previous command|
|!?|References previous command's arguements|

### Directing Input and Output

#### Standard input and standard ouput

**Standard input**

* stdin
* keyborad
* /dev/stdin

**Standard output**

* stdout
* text terminal
* /dev/stdout


#### Directing output to a file

	sort file.txt > sorted_file.txt

This command will overwrite *file.txt* 

#### Appending to a file

	echo 'Hello World' >> file.txt
	
* Adds 'Hello World' to file.txt instead of overwriting the entire file.

#### Directing input from a file

	sort < file.txt
	
* The arguements must be files

#### Piping output to input

	echo 'hello world' | wc
	
* Piping it into a command instead of a file.

#### Suppressing output

/dev/nul

* "null device", "bit bucket", "black hole"
* Similar to special files /dev/stdin and dev/stdout
* Unix discards any data sent there

### Configuring Your Working Environment

#### Profile, login, and resource files

**Upon login to a bash shell**

* /etc/profile
	* master default commands that every Mac user receives
* ~/.bash_profile,~/.bach_login,~/.profile,~/.login
	* personal customization
	
**Upon starting a new bash subshell**

* ~/.bashrc

**Upon logging out of bash shell**

* ~/.bash_logout

###### Bash Shells: Login v. Non-login

	if [ -f ~/.bashrc ]; then
		source ~/.bashrc
	fi
	
	* Put all shell configuration in ~/.bashrc
	


#### Setting command aliases

alias ll= `ls -lah`

remove alias e.g.
	
	unalias
	
aliases' only last for the current login

Defined aliases can be done in configuration files


#### Setting and exporting environment variables

	source .bashrc
	*	configures the .bashrc file with your computer

#### Setting the PATH variable

	nano .bashrc
	EXPORT PATH="usr/local/bin:"

#### Configuring history with variables

	nano .bashrc
There are 5 different variables that can be configured:

1. export HISTSIZE=1000

	* Number of commands that history will rememember. The default if 500.

2. export HISTFILESIZE=100000

	* Maximum size that history file is allowed to become.

3. export HISTTIMEFORMAT='%b %d %I: %M %p'

	* Provides a time stamp next to your history entries, letting you know when they were added. THis is also known as strftime format.

4. export HISTCONTROL='ignoreboth'

	**Three values**

	* ignoreboth- Ignores both, ignoreups & ignorespace.
	* ignoredups- Will not record duplicate lines multiple times
	* ignorespace- Ignores entries starting space. 

5. export HISTIGNORE="history:pwd:ls -lah"

	* A list of commands you want ignored all of the time.
	

#### Customizing the command prompt

	nano .bashrc
	export PS1="\W"

|**Code**|**Command Prompt Output**|
|-----|-----|
|\u|username|
|\s|current shell|
|\w|current working directory|
|\W|basename of current working directory|
|\d|date in "weekday month date" format|
|\D{format}|date in strftime format ("%Y-%m-%d")|
|\A|time in 24-hour HH:MM format|
|\t|time in 24-hour HH:MM:SS format|
|\@|time in 12-hour HH:MM am/pm format|
|\T|time in 12-hour HH:MM:SS format|
|\H|hostname|
|\h|hostname up to first "."|
|\!|history number of this command|
|\$|when UID is 0(root), a "#", otherwise a "$"|
#### Logout file


### Unix Power Tools

#### grep: Searching for matching expressions

* grep
	* Output all lines matching a regular expression
	* Global Regular Expression Print
		* In Unix ed editor: g/re/p
* Regular Expression
	* Expression for describing a pattern in text strings
	* "regex" for short
* Useful in other contexts
	* Most programming languages
	* Many text editors


`grep 'word' file.txt`

* Search is case sensitive. `-i` to disable case sensitivity
* `-w` will only match whole words
* `-v` will invert the match
* `man grep` for more options 

#### grep: Multiple files, other input

	grep -R word /Users/Maksim/unix_files/
	* Recursively searchs 'word' in listed subdirectories 

#### grep: Coloring matched text

	grep --color file.txt
* Mark up the matching text with the expression stored in GREP_COLOR environment variable

#### Introduction to regular expressions



#### Regular expressions: Basic syntax

![Regular Expression Basics](/Users/maksim/Desktop/Screen Shot 2015-06-03 at 6.08.29 PM.png)

#### Using regular expresions with grep



#### tr: Translating characters

	tr '(search string)' '(replacement string)' e.g.
	input: echo 'a,b,c' | tr ',' ':'
	output: a:b:c 

#### tr: Deleting and squeezing characters

**tr options**

|option|description|
|---|---|
|-d|delete characters in listed set|
|-s|squeeze repeats in listed set|
|-c|use complementary set|
|-dc|delete characters not in listed set|
|-sc|squeeze characters not in listed set
#### sed: Stream editor

modifies stream of input according to a stream of commands before producing the output.

Most common usage is for doing substitutions.

	sed 's/a/b'
	
* s: substitution
* a: seach string
* b: replacement string

Different from grep, because it does not execute commands globally. It only changes the first occurence. However, if a user wants to execute commands globally then he would need to add a 'g'. e.g.

	sed 's/a/b/g'


#### sed: Regular expressions and back-references



#### cut: Cutting select text potions
	
	cut (-c, -b, -f) (characters) (file name)

	cut -c 1-5 newfile.txt

* b= bytes
* c= characters
* f= fields

#### diff: Comparing files

diff is usseful for comparing two files.

	diff oldfile.txt newfile.txt
	
* d= deleted
* a= appended
* c= changed

**diff comparison options**

|option|description|
|----|----|
|-i|case insensitive|
|-b|ignore changes to blank characters|
|-w|ignore all whitespace|
|-B|ignore blank lines|
|-r|recursively compare directories|
|-s|show identical files|

#### diff: Alternative formats

**diff output formats**

|option|description|
|---|---|
|-c|copied context|
|-u|unified context|
|-y|side-by-side|
|-q|only whether files differ|

	diff -c oldfile.txt newfile.txt
#### xargs: Passing argument lists to commands

xargs is short for, execute as arguments. Xargs, parses an input stream into items, then loops through each item in that list and passes it to a command. e.g.

	echo 'file.txt' | xargs wc
	
Able to pass multipe arguments

	echo 'greenfile.txt orangefile.txt' | xargs wc

#### xargs: Usage examples


