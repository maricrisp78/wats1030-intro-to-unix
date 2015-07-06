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
/home/cabox/workspace 

* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`?* 
LICENSE  README.md  challenge_files  nix_scavenger_hunt.md  nix_scavenger_hunt_stretch.md

* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. *How are the results different when you use the `-alh` options?*
total 36K                                                                                                                                                                
drwxrwxr-x 4 cabox cabox 4.0K Jun 30 22:48 .                                                                                                                             
drwxr-xr-x 9 cabox cabox 4.0K Jun 30 22:48 ..                                                                                                                            
drwxrwxr-x 8 cabox cabox 4.0K Jul  1 22:43 .git                                                                                                                          
-rw-rw-r-- 1 cabox cabox 1.1K Jun 30 22:48 LICENSE                                                                                                                       
-rw-rw-r-- 1 cabox cabox 1.4K Jun 30 22:48 README.md                                                                                                                     
drwxrwxr-x 7 cabox cabox 4.0K Jun 30 22:48 challenge_files                                                                                                               
-rw-rw-r-- 1 cabox cabox 5.3K Jun 30 22:50 nix_scavenger_hunt.md                                                                                                         
-rw-rw-r-- 1 cabox cabox  317 Jun 30 22:48 nix_scavenger_hunt_stretch.md                                                                                                 

* The `man` ("manual") command tells you more about how any given command works. Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?*
-bash: man: command not found - (I used my terminal to type in man ls and the output is below)
  -a  Include directory entries whose names begin with a dot (.).
  -h  When used with the -l option, use unit suffixes: Byte, Kilobyte,
      Megabyte, Gigabyte, Terabyte and Petabyte in order to reduce the
      number of digits to three or less using base 2 for sizes.
  -l  (The lowercase letter ``ell''.)  List in long format.  (See
	  below.)  If the output is to a terminal, a total sum for all the
	  file sizes is output on a line before the long listing.




* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed?*
bin  boot  dev  etc  fastboot  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var      

* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:*
-bash: /: Is a directory   

* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:*
cd: usage: cd [-L|[-P [-e]] [-@]] [dir] 
-bash: pwd: -c: invalid option                                                                                                                                           
pwd: usage: pwd [-LP]  

* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?*
cabox@box-codeanywhere:~/workspace$ challenge_files                                                                                                                      
-bash: challenge_files: command not found                                                                                                                                
cabox@box-codeanywhere:~/workspace$ cd                                                                                                                                   
cabox@box-codeanywhere:~$ cd challenge_files                                                                                                                             
-bash: cd: challenge_files: No such file or directory                                                                                                                    
cabox@box-codeanywhere:~$ cd challenge_files                                                                                                                             
-bash: cd: challenge_files: No such file or directory   

* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?*
cabox@box-codeanywhere:~$

* Press the up arrow on your keyboard. *What just happened?* 
Repeated the last command

* Press the up arrow a few more times. *What do you see?*
Repeated the last several commands I wrote

* Run the `history` command. *What do you see?*
It listed every command I have typed out

### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?*
cabox

* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:*
cabox    pts/0        Jul  1 23:35 (54.69.152.243)     

* How long has your system been running? Use `uptime` to see, and *paste the result here:*
23:57:05 up 21 min,  1 user,  load average: 0.00, 0.00, 0.00 

* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?*
I do not know how to interpret what I see here
USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND                                                                                                 
root         1  0.0  0.4  33188  2572 ?        Ss   23:35   0:00 init                                                                                                    
root         2  0.0  0.0      0     0 ?        S    23:35   0:00 [kthreadd/400058]                                                                                       
root         3  0.0  0.0      0     0 ?        S    23:35   0:00 [khelper/400058]                                                                                        
root       151  0.0  0.1  19428   816 ?        S    23:35   0:00 upstart-udev-bridge --daemon                                                                            
root       182  0.0  0.2  49216  1392 ?        Ss   23:35   0:00 /lib/systemd/systemd-udevd --daemon                                                                     
syslog     295  0.0  0.2 184188  1444 ?        Ssl  23:35   0:00 rsyslogd                                                                                                
root       378  0.0  0.5  61316  3072 ?        Ss   23:35   0:00 /usr/sbin/sshd -D                                                                                       
root       415  0.0  0.1  15608  1028 ?        S    23:35   0:00 upstart-socket-bridge --daemon                                                                          
root       422  0.0  0.1  15492   864 ?        S    23:35   0:00 upstart-file-bridge --daemon                                                                            
root       432  0.0  0.5  71260  2652 ?        Ss   23:35   0:00 /usr/sbin/apache2 -k start                                                                              
www-data   435  0.0  0.4 415720  2416 ?        Sl   23:35   0:00 /usr/sbin/apache2 -k start                                                                              
www-data   436  0.0  0.4 415720  2420 ?        Sl   23:35   0:00 /usr/sbin/apache2 -k start                                                                              
root       503  0.0  0.1  12740   848 tty1     Ss+  23:35   0:00 /sbin/getty 38400 console                                                                               
root       505  0.0  0.1  12740   852 tty2     Ss+  23:35   0:00 /sbin/getty 38400 tty2                                                                                  
root       514  0.0  0.6  63876  3336 ?        Ss   23:35   0:00 sshd: cabox [priv]                                                                                      
cabox      516  0.0  0.2  64012  1484 ?        S    23:35   0:00 sshd: cabox@notty                                                                                       
cabox      517  0.0  0.2  13440  1256 ?        Ss   23:35   0:00 /usr/lib/openssh/sftp-server                                                                            
root       518  0.0  0.6  63876  3480 ?        Ss   23:35   0:00 sshd: cabox [priv]                                                                                      
cabox      520  0.0  0.2  63876  1468 ?        S    23:35   0:00 sshd: cabox@pts/0                                                                                       
cabox      521  0.0  0.3  18128  2032 pts/0    Ss   23:35   0:00 -bash                                                                                                   
cabox      560  0.0  0.2  15520  1136 pts/0    R+   23:57   0:00 ps aux   

* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?*
top - 00:02:06 up 26 min,  1 user,  load average: 0.00, 0.00, 0.00                                                                                                       
Tasks:  21 total,   1 running,  20 sleeping,   0 stopped,   0 zombie                                                                                                     
%Cpu(s):  0.0 us,  0.0 sy,  0.0 ni,100.0 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st                                                                                          
KiB Mem:    524288 total,    28656 used,   495632 free,        0 buffers                                                                                                 
KiB Swap:   524288 total,        0 used,   524288 free.    17856 cached Mem                                                                                              
                                                                                                                                                                         
  PID USER      PR  NI    VIRT    RES    SHR S  %CPU %MEM     TIME+ COMMAND                                                                                              
  561 cabox     20   0   19828   1408   1056 R   0.3  0.3   0:00.11 top                                                                                                  
    1 root      20   0   33188   2572   1448 S   0.0  0.5   0:00.33 init                                                                                                 
    2 root      20   0       0      0      0 S   0.0  0.0   0:00.00 kthreadd/400058                                                                                      
    3 root      20   0       0      0      0 S   0.0  0.0   0:00.00 khelper/400058                                                                                       
  151 root      20   0   19428    816    584 S   0.0  0.2   0:00.04 upstart-udev-br                                                                                      
  182 root      20   0   49216   1392    948 S   0.0  0.3   0:00.00 systemd-udevd                                                                                        
  295 syslog    20   0  184188   1444    948 S   0.0  0.3   0:00.00 rsyslogd                                                                                             
  378 root      20   0   61316   3072   2392 S   0.0  0.6   0:00.00 sshd                                                                                                 
  415 root      20   0   15608   1028    404 S   0.0  0.2   0:00.00 upstart-socket-                                                                                      
  422 root      20   0   15492    864    388 S   0.0  0.2   0:00.00 upstart-file-br                                                                                      
  432 root      20   0   71260   2652   1472 S   0.0  0.5   0:00.03 apache2                                                                                              
  435 www-data  20   0  415720   2416    908 S   0.0  0.5   0:00.21 apache2                                                                                              
  436 www-data  20   0  415720   2420    912 S   0.0  0.5   0:00.22 apache2                                                                                              
  503 root      20   0   12740    848    700 S   0.0  0.2   0:00.00 getty                                                                                                
  505 root      20   0   12740    852    704 S   0.0  0.2   0:00.00 getty                                                                                                
  514 root      20   0   63876   3336   2584 S   0.0  0.6   0:00.00 sshd                                                                                                 
  516 cabox     20   0   64012   1492    712 S   0.0  0.3   0:00.01 sshd                                                                                                 
  517 cabox     20   0   13576   1300    752 S   0.0  0.2   0:00.00 sftp-server                                                                                          
  518 root      20   0   63876   3480   2728 S   0.0  0.7   0:00.00 sshd                                                                                                 
  520 cabox     20   0   64012   1492    724 S   0.0  0.3   0:00.06 sshd                                                                                                 
  521 cabox     20   0   18128   2032   1544 S   0.0  0.4   0:00.02 bash                                                                                                 
                                                                               

### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?*
-bash: cd: challenge_files: No such file or directory

* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?*
Options:                                                                                                                                                                 
  -d        display help instead of ring bell                                                                                                                            
  -f        count logical, rather than screen lines                                                                                                                      
  -l        suppress pause after form feed                                                                                                                               
  -p        suppress scroll, clean screen and disblay text                                                                                                               
  -c        suppress scroll, display text and clean line ends                                                                                                            
  -u        suppress underlining                                                                                                                                         
  -s        squeeze multiple blank lines into one                                                                                                                        
  -NUM      specify the number of lines per screenful                                                                                                                    
  +NUM      display file beginning from line number NUM                                                                                                                  
  +/STRING  display file beginning from search string match                                                                                                              
  -V        output version information and exit                                                                                                                          


* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?*
It listed a huge long list of stuff

* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?*
Usage: grep [OPTION]... PATTERN [FILE]...                                                                                                                                
Try 'grep --help' for more information.   
-bash: challenge_files: command not found  

* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*
(from my mac terminal)
usage: grep [-abcDEFGHhIiJLlmnOoqRSsUVvwxZ] [-A num] [-B num] [-C[num]]
	[-e pattern] [-f file] [--binary-files=value] [--color=when]
	[--context[=num]] [--directories=action] [--label] [--line-buffered]
	[--null] [pattern] [file ...]
	
### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?*
Applications
Creative Cloud Files
Desktop
Documents
Downloads
Dropbox
Library
Movies
Music
Pictures
Public
files.txt
maricrisp78
maricrisp78.github.io

* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.*
(from my mac terminal)
total 72
drwxr-xr-x+ 26 marieporciuncula  staff   884B Jul  5 23:21 .
drwxr-xr-x   6 root              admin   204B May 22 16:58 ..
-r--------   1 marieporciuncula  staff     7B Jun  3 13:09 .CFUserTextEncoding
-rw-r--r--@  1 marieporciuncula  staff    10K Jun 25 21:44 .DS_Store
drwx------  47 marieporciuncula  staff   1.6K Jul  5 21:15 .Trash
-rw-------   1 marieporciuncula  staff   397B Jul  5 23:17 .bash_history
drwxr-xr-x   3 marieporciuncula  staff   102B May 23 14:36 .config
drwx------   9 marieporciuncula  staff   306B Jul  2 20:43 .dropbox
-rw-r--r--   1 marieporciuncula  staff   464B Jun 28 13:13 .gitconfig
-rw-r--r--@  1 marieporciuncula  admin    13B Feb  3 10:33 .gitignore_global
-rw-r--r--@  1 marieporciuncula  admin    27B Feb  3 10:33 .hgignore_global
drwx------   5 marieporciuncula  staff   170B May 23 14:36 .ssh
drwx------   4 marieporciuncula  staff   136B May 22 21:40 Applications
drwx------@  9 marieporciuncula  staff   306B May 24 19:14 Creative Cloud Files
drwx------+ 24 marieporciuncula  staff   816B Jul  5 20:38 Desktop
drwx------+ 10 marieporciuncula  staff   340B Jun 28 23:18 Documents
drwx------+ 25 marieporciuncula  staff   850B Jul  4 12:50 Downloads
drwx------@  7 marieporciuncula  staff   238B Jul  2 20:43 Dropbox
drwx------@ 49 marieporciuncula  staff   1.6K Jun  7 00:35 Library
drwx------+  3 marieporciuncula  staff   102B May 22 16:57 Movies
drwx------+  3 marieporciuncula  staff   102B May 22 16:57 Music
drwx------+  4 marieporciuncula  staff   136B Jun  6 13:24 Pictures
drwxr-xr-x+  5 marieporciuncula  staff   170B May 22 16:57 Public
-rw-r--r--   1 marieporciuncula  staff   151B Jul  5 23:21 files.txt
drwxr-xr-x   9 marieporciuncula  staff   306B Jun 28 13:01 maricrisp78
drwxr-xr-x   9 marieporciuncula  staff   306B Jun 28 13:18 maricrisp78.github.io

* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:*
(from my mac terminal)
marieporciuncula  3125   0.0  0.0  2461020    504 s000  U+   11:28PM   0:00.00 grep maricrisp78