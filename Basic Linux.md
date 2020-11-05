### Deleting files 😸
* `rm file` removing file
* `rm -r dir` removing the directory and all the content
* `rm -f file` force removing file without prompting 
* `rm s*` removing file and directory with the first character s
* `rm .*` removing the file and folder with the first character is . 

### Copying files 😸
* `cp source_file directory_file` copying 1 file into dest directory
* `cp src_file1 src_fileN dest_dir` copying more file into dest directory
* `cp -i` copying with interactive mode
* `cp -r source_directory destination` copying dir/file to dest dir, when dest dir not exist then create

### Moving files and renaming files 😸
* `mv` this command can use for renaming and moving file/dir
* `mv src dest`
* `mv -i src dest`

### Compress files and creating archives 😸
**tar**
* `tar [-] c|x|t tarfile [pattern]`
* `tar cf test.tar tes1` example
* `tar xvf test.tar` example
* `tar zcf test.tgz/tar.gz tes1` example

**tar options**
* `c` opt for create tar
* `x` opt for extart tar
* `t` opt for read content tar
* `v` opt for verbose (diplaying details about name file is process)
* `z` opt for using compression
* `f file` use the file

**compressing file to save space**
* `gzip data` example (output file data.gz)
* `gzip` for compressing data
* `gunzip` for uncompressing data
* `gzcat/zcat` for read the content trought the termainal/cli or internet says another way for uncompressing data

## Wildcards 😸
* `*` matches zero or more char
* `ls fil*` example

* `?` matches exacly one char
* `ls f?le` example

* `[]` a char class
* `ls ca[nt]*` example
* `[!aiueo]*` example
* `[a-g]*` example
* `[3-6]*` example

* `[[:alpha:]]`
* `[[:alnum:]]`
* `[[:digit:]]`
* `[[:lower:]]`
* `[[:space:]]`
* `[[:upper:]]`
* `ls *[[:digit:]]` example

* `\` for match a wildcard char
* `*\?` example

## I/O and Redicrection 😸
I/O name | Abbreviaition | File Descriptor
--- | --- | ---
Standartd Input | stdin | 0
Standard Output | stdout | 1
Standart Error | stderr | 2

### Redirection
* `>` redirect stdout to a file = overwrite existing content
* `>>` redirect stdout to a file = append to any existing content
* `<` redirect input from a file to commmand
* `&` used with direction to signal that a file descriptor being used

### The null device
* `> /dev/null/` redirect output to nowhere / passing to null device it / passing and not save the log

* `ls file1 not-here > out` example
* `sort < file1 > out` example
* `ls -l 1> out` example
* `ls >> out`example
* `ls file1 not-here 1> out 2> out.err` example
* `ls file1 not-here 1> out.both 2>&1` example

## Comparing files 😸

* `diff file1 file2` compare two file
* `3c3 = LineNumFile1-Action-LineNumFile2`
* `Action = (A)dd (C)hange (D)elete`
* `sdiff file1 file2` side-by-side comparison
* `vimdiff file1 file2` Highlight different in vim
vimdiff
* `ctrl+w / w` goto the next window
* `q` quit (close current windows)
* `qa` quit all
* `qa!` force quit all

## Searching in File and using Pipe 😸
### grep
* `prep`
* `grep pattern file`
### grep Option
* `-i` ignoring case 
* `-c` counting line the match search
* `-n` line numbering the match search
* `-v` inverse the search pattern
### example grep
* `grep user file1`
* `grep o file1`
* `grep -v o file1`
* `grep -i User file1`
* `grep -ci User file1`
* `grep -ni User file1`


### The File Command
`file file_name` display the file type
### example file
`file sales.data`
`file *`

### Searching for text in Binary files
* 'strings' display printable strings

### Pipes
`|` pipe symbol
`command-output | command-input`
`grep pattern file` is the same `cat file | grep pattern`

### the cut command
`cut [file]`
### cut Option
`-d delimiter`
`-f N`

## example grep / pipes / cut command / strings 😸
* `strings lagu.mp3 | grep -i aldiano | cut -d " " -f2`
* 'grep bob /etc/password | cut -d: -f1,5 | sort | tr ":" " " | column -t'

### piping output to a Pager
* `more`
* `less`
### example
* `cat /etc/passwd | less` is same as `less /etc/passwd`


## Transferring and Copying Files Over the Network 😸
### scp / sftp command line utilities
`scp` - secure copy
`sftp` - SSH file transfer protocol
both is secure file transfer protocol

`ftp` - file transfer protocol
ftp is not secure is mean your login creadential its just send into plain text over the network, just choose scp / sftp for file transfer protocol

`scp source destination`
`sftp host`
### example scp / sftp
`scp file1.txt linuxsvr:/tmp/`
`scp file1.txt adminuser@linuxsvr:~`
`sftp adminuser@linuxsvr`

## Cutomizing the Shell Prompt 😸
use the environment varible to customize
`bash, ksh, and sh` use `$PS1`
`csh, tcsh, zsh` use $prompt

### Customizing the prompt with PS1
* `\d` Date in "Week Month Date" format "Tue May 21"
* `\h` Hostname to the first period
* `\H` Hostname
* `\n` Newline
* `\t` Current time in 24-hour HH:MM:SS format
* `\T` Current time in 12-hour HH:MM:SS format
* `\@` Current time in 12-hour am/pm format
* `\A` Current time in 24-hour HH:MM format
* `\u` Username of the current user
* `\w` Current working directory
* `\W` Basename of the current working directory
* `\$` if the effective UID id 0, a #, otherwise a $ - its show $ for normal user and its show # for superuser / root account

### example
`echo $PS1`
`PS1="\u@\h \$"`
`vi .bash_profile`


## Using Aliases 😸
* `alias` see the list of aliases
* `alias name=value` creating alias
* `alias name` removing alias

### example Aliases
* `alias cls="clear"`


## Environment Variables 😸
* `printenv` for viewing environment variable

env variable can set on `~/.bash_profile`


### example
* `printenv HOME`
* `echo $HOME`

### Creating env variable
* `export VAR="value"`

### example
* `export EDITOR="vi"`
* `export TZ="US/Pasific"`

### Removing env variable
* `unset VAR`

## Processes and Job Control 😸
* `ps` display process status
### ps option
* `-e` everything, all processes
* `-f` full format listing
* `-u username` display username's processes
* `-p pid` display information for PID

* `ps -p 1715` example

### common ps commands
* `ps -e` diplay all processes
* `ps -ef` display all processes, full
* `ps -eH` display a process tree
* `ps -e --forest` display a process tree
* `ps -u username` display user's processes
* `ps -fu root` example

### other ways to view processes
* `pstree` display process in a three format
* `top` interactive process viewer
* `htop` interactive process viewer

### backgroung and foregroung processes
* `command &` start command in background
* `ctrl + c` kill the foreground process
* `ctrl + z` suspend the foreground process
* `bg [%num]` background a suspended process
* `fg [%num]` foreground a background process
* `kill` kill a process by job number or PID
* `job [%num]` list jobs

### killing process
* `ctrl+c` kills the foreground process
* `kill [-sig] pid` send a signal to a process
* `kill -l` display a list of signals

* `kill 123`
* `kill -15 123`
* `kill -TERM 123`

### example
* `./long-running-program &`
* `jobs` see running process in foreground
* `jobs %% \ %+` see the current job
* `jobs %-` see the previous job
* `fg %2 / 2` take process number 2 to foreground
* `bg %1` take process to the background / start process
* `kill %1`
* `fg %3` is same as `%3`
* `kill 1715`
* `kill -l` list command kill / see all list TERM
* ``

## Scheduling Repeated Jobs with Cron 😸
* `cron` A time based job scheduling service 
* `crontab` A program to create, read, update, and delete your job schedule
* use cron to schedule and automated tasks

Crontab format
* `* * * * * commmand` - (minute 0-59 | hour 0-23 | day of the month 1-31 | month of the year 1-12 | day of the week 0-6)

### example
* `0 7 * * 1 /opt/sales/bin/weekly-report` run every Monday at 07:00
* `0 2 * * * /root/backupdb > /tmp/db.log 2>&1` send output to a log file / redirecting output
* `0,30 * * * * /opt/acme/bin/half-hour-check` run every 30 minutes
* `*/2 * * * * /opt/acme/bin/half-hour-check` run every 30 minutes
* `0-4 * * * * /opt/acme/bin/first-five-mins` run for the first 5 minutes of the hour

### crontab shortcut

shortcut | default syntax
--- | ---
`@yearly` | `0 0 1 1 *`
`@annually` | `0 0 1 1 *`
`@monthly` | `0 0 1 * *`
`@weekly` | `0 0 * * 0`
`@daily` | `0 0 * * *`
`@midnight` | `0 0 * * *`
`@hourly` | `0 * * * *`

### Using the Crontab Command
* `crontab file` Install a new crontab from file
* `crontab -l` List your cron jobs
* `crontab -e` Edit your cron jobs
* `crontab -r` Remove all of your cron jobs


## Switching User and Running Commands as Other 😸
### The su command
* `su [username]` change user ID or become superuser

### su Options
* `-` A hypen is used to provide an environment similiar to what the user would expect had the user loggin in directly
* `-c command` Specify a command to be executed

* `whoami` display the username

### example
* `su oracle` change user to oracle
* `su - oracle` change user and the env to oracle
* `su -c 'echo $ORACLE_HOME' - oracle` send command to oracle env without changing user

### sudo - superuser do
* `sudo` execute a command as another user, typically the superuser

### using sudo
* `sudo -l` list available commands
* `sudo command` and `sudo -u root` run command as roo acc
* `sudo -u user command` run as user
* `sudo su` swict to the superuser acc
* `sudo su -` switch to the superuser acc with root env
* `sudo su - username` switch to the username acc
* `sudo -s` and `sudo -u root -s` start shell
* `sudo -u user -s` start a shell as user

### example
* `sudo /etc/init.d/oracle start`
* `sudo -u bob /opt/bobapp/bin/start`
* `sudo su - oracle`
* `sudo -s`

## Changing the sudo Configuration
* `visudo` edit the /etc/sudoers file

### sudoers format
* `user host=(user)[NOPASSWD:]commands`
### example
* `adminuser ALL=(ALL)NOPASSWD:ALL`
* `jason linuxsvr=(root)/etc/init.d/oracle`


## Shell History and Tab Completion 😸

### Shell history
execute commands are added to the history
Shell history is store in memory on disk
* `~/.bash_history`
* `~/.history`
* `~/.histfile`

### history COMMAND
* `history` display the shell history
* `HISTSIZE` control the numberr of commands to retain in history
* `export HISTSIZE=1000`

### ! Syntax
* `!N` repeat command line number N
* `!!` repeat the previous command line
* `!string` repeat the most recent command starting with "string"

### More ! syntax
* `!:N` <Event> <Separator> <word>
* `!` represent a command line (or event) / the most recent command line
* `:N` represent a word on the command line - 0 = command, 1 = first argument, etc

### even more ! syntax
* `!^` represent the first argument, is same to !:1
* `!&` represent the last argument

### Searching Shell history
* `ctrl-r` reverse shell history search
* `enter` execute the command
* `arrows` change the command
* `crtl+g` cancel the search


### Tab Completion
* `tab` autocompletion

### example
* `echo !:2`
* `!e`
* `echo !^ !l:2 delta !l:0`

## Installing Software 😸
### RPM Distros
* RedHat
* `CentOS`
* `Fedora`
* `Oracle Linux`
* `Scientific Linux`
### Installing on RPM
yum
* `yum search string` search for string
* `yum info [package]` display info
* `yum install [-y] package install package`
* `yum remove package` remove package

rpm
* `rpm -q1` list all installed packages
* `rpm -qf /path/to/file` list the files package
* `rpm -ql package` list package's files
* `rpm -ivh package.rpm` install package
* `rpm -e package` erase (uninstall) package

### DEB Distros
* Debian
* Linux Mint
* Ubuntu

### installaing on DEB
APT - Advance packaging Tool
* `apt-cache search string` search for string 
* `apt-get install [-y] package` install package
* `apt-get remove package` remove package, leaving configuration
* `apt-get purge package` remove package, deleting configuration
* `apt-cache show package` display information about package

dpkg
* `dpkg -l` list installed packages
* `dpkg -D /path/to/file` list file's package

dpkg
* `dpkg -L package` list all files in package
* `dpkg -i package.deb` install package

## Other 😸

**SORT**
* `sort file` to sorting content of file
* `sort -ru -k2 file1` example1

**SORT OPTIONS**
* `-k F` opt for selecting sort by row (F=row/field)
* `-r` ort for reversing sort
* `-u` opt for to take only unique value 

**disk usage**
* `du` estimating file usage
* `du -k` displaying in kilobyte
* `du -h` displaying in human readable

**other**
* `ls s*` showing file/directory with the first character s
* `ls -d s*` showing directory with the first char is .
* `cat file1` to read the content in file

### Insight 😸
```
1. Perbedaan achiving dengan compressing!
   - Archiving memasukkan data kedalam rar, tar, tgz, dll
   - Compressing sama dengan archiving namun dapat merubah data menjadi lebih  kecil / ringan (compressing data)
2. Perbedaan SIGTERM dan SIGKILL
   - SIGTERM ini adalah menghentikan sebuah proses yang berjalan dengan cara "halus". Setelah sinyal SIGTERM dikirim maka proses terminate akan dilakukan secara berurutan dimulai dari pemutusan koneksi socket, penghapusan berkas temp, penginformasian ke sub-proses bahwa proses induknya mati, dan seterusnya.
   - Berbeda dengan SIGTERM dimana proses akan dihentikan secara halus dan berurutan, maka SIGKILL  akan menghentikan proses dengan cepat setelah sinyal dikirim, Imbas dari penghentian proses secara kasar ini mungkin saja masih ada berkas temporary yang tertinggal, atau proses lain yang terhubung dengan PID yang kita hentikan akan tiba-tiba error. Namun SIGKILL ini efektif untuk menghentikan paksa proses yang hang ataupun tidak bisa dihentikan secara normal menggunakan SIGTERM.
```
