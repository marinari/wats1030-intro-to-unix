# *nix Scavenger Hunt

Complete the following challenges using the command-line interface on your favorite
Unix or Linux operating system. You are welcome and encouraged to consult any
additional documentation online or in books.

Please add your answers/responses/text pastes to the document after each prompt.

Note: For some of the challenges you will need to reference files included with
this repository, so you will need to fork the repo into your own Github account
and then clone it to your development environment.

## The Challenges

### Navigating the Filesystem

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. *Paste the output of the `pwd` command here:*
/Users/ariannamarin/Projects/wats1030-intro-to-unix
* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`?*
LICENSE				challenge_files			nix_scavenger_hunt_stretch.md
README.md			nix_scavenger_hunt.md
* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. *How are the results different when you use the `-alh` options?*
total 40
drwxr-xr-x    8 ariannamarin  staff   272B Apr 10 13:02 .
drwxr-xr-x   12 ariannamarin  staff   408B Apr 10 13:02 ..
drwxr-xr-x   13 ariannamarin  staff   442B Apr 10 13:02 .git
-rw-r--r--    1 ariannamarin  staff   1.1K Apr 10 13:02 LICENSE
-rw-r--r--    1 ariannamarin  staff   1.3K Apr 10 13:02 README.md
drwxr-xr-x  111 ariannamarin  staff   3.7K Apr 10 13:02 challenge_files
-rw-r--r--    1 ariannamarin  staff   5.5K Apr 10 13:05 nix_scavenger_hunt.md
-rw-r--r--    1 ariannamarin  staff   317B Apr 10 13:02 nix_scavenger_hunt_stretch.md
Alh options allows me to see more details about each of the files within a directory. This includes the last time the file was changed and who created the file.
* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: http://linux.die.net/man/)Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?*
ls -a : Include directory entries whose names begin with a dot (.).
ls -h: When used with the -l option, use unit suffixes: Byte, Kilobyte, Megabyte,
             Gigabyte, Terabyte and Petabyte in order to reduce the number of digits to
             three or less using base 2 for sizes.
ls -l: List in long format and include total sum of all file sizes within the chosen directory.

* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed?*
Applications	Documents	Library		Music		Projects
Desktop		Downloads	Movies		Pictures	Public

* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:* Cecelia-MacbookPro-2015:Projects ariannamarin$ cd /
Cecelia-MacbookPro-2015:/ ariannamarin$
_I am familiar with this command because I use another version of it which is `cd ..`_

* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:*
Cecelia-MacbookPro-2015:/ ariannamarin$ cd ~
Cecelia-MacbookPro-2015:~ ariannamarin$ pwd
/Users/ariannamarin

* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?* 3
* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?* back in Projects folder
* Press the up arrow on your keyboard. *What just happened?* the last command executed
* Press the up arrow a few more times. *What do you see?* the previous commands executed before the most recent
* Run the `history` command. *What do you see?* A list of all the commands ever executed in the terminal including when I ran 'history'.

### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?*
ariannamarin
* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:* ariannamarin console  Jan 11 10:31
ariannamarin ttys000  Mar  6 12:29
I don't have any additional users set up, and I am not sure what console and ttys000 are.
* How long has your system been running? Use `uptime` to see, and *paste the result here:* 13:50  up 90 days,  2:11, 2 users, load averages: 1.43 1.28 1.24
* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?* It looks like its running the time and stats for all the applications on my computer. This includes the time the application started and the percentage of memory the file takes up. The manual describes 'ps' as process status command.  
* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?*
Top shows an current and constantly updating run down of all the applications that are currently running on the machine.

### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?* 2
* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?* 1-15-2015
* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?* ./tmp/modi_laboriosam.txt
the period in this instance is for the current directory which is "challenge_files"
* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?* 2
* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*
serial-numbers/eaque_molestiae.txt

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?* All the files that are in the challenge_files directory are within that .txt file created from the ls command
* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.* the files listed are organized in a chart format
* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:*
I'm doing this exercise on my personal machine and not within the Code Anywhere environment so the processes running are a lot longer and more complex and contain personal secure information that I don't want to share via github. I will take a screenshot of a section of the code from my terminal and add that file to this repo in order to fulfill this to-do. 
