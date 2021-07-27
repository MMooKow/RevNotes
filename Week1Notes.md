# Week One Notes

Merge conflict- Dev A and Dev D work on common file test.txt. Both writing code in their own local copies. Dev A makes a push to file and same thing is pushed by Dev D. Might be Overlap.

GIT Workflow

Live(Master) --> User access                                       <---|
|                                                                      |
|-->Feature branch 1   Dev 1 -->  git merge adds directly to master    |  BAD
|
|-->Feature branch 2   Dev 2  --> git pull request -> code review/ peer review. GOOD
|
|-->Feature branch 3   Dev 3

----------------
| Project         |
| Project Lead    |
| Team lead/lead  |
| SSE             |
| SE              |
| Junior SE       |
 -----------------

Unix/bash command - `vi 'path'` Creates new file and opens in vim. Press i and select insert to add text. Esc -> shift + z + z to exit vim
`git branch` see how many branches you have

`git checkout -b feature-1`
git checkout (branch) branchName*Creates local branch*

`git push --set-upstream origin feature-1`
*Uploads local branch to server*

`git checkout main`
*switch branch to main*

`git merge feartue-1`
*Merge branch directly to main*

1 `git branch`
2 `git checkout -b branch-name`
3 `write changes to test.txt`
4 `git add test.txt`
5 `git commit -m 'message'`
6 `git push --set-upstream origin 'branch-name`

***Note: If you clone a repo, you dont need to init as well. 
When you run git clone <repo_url> to clone a repository, the default remote origin is created automatically. If the repository is created by git init, there is no default remote, no origin. You need to set it up by yourself.

git remote add origin <repo_url>
repo_url is the path to an existing remote repository which you want to exchange data with . If it's in the local disk, it could be file:///home/me/foo.git or /home/me/foo.git. If it's hosted in Github, it could be https://github.com/me/foo.git or ssh://git@github.com/me/foo.git.***

FILE MANAGEMANT
reference following section: <https://www.tutorialspoint.com/unix/unix-file-management.htm>

Unix commands:
    `ls` lists files in current directory(folder)
    `ls -i` gives additional info about files in current directory
        $ ls -l
        total 59
        -rw-r--r-- 1 MMooKow 197609 4534 Jul 27 10:52 FCC-Portfolio.css
        -rw-r--r-- 1 MMooKow 197609 1818 Jul 27 10:52 FCC-Portfolio.html
        -rw-r--r-- 1 MMooKow 197609  555 Jul 27 10:52 FCC-Portfolio.js
        -rw-r--r-- 1 MMooKow 197609 5316 Jul 27 10:52 FCC-ProductLanding.css
        -rw-r--r-- 1 MMooKow 197609 2083 Jul 27 10:52 FCC-ProductLanding.html
        -rw-r--r-- 1 MMooKow 197609 1272 Jul 27 10:52 FCC-RecordCollection.js
        -rw-r--r-- 1 MMooKow 197609   82 Jul 27 10:52 FCC-SurveyForm.css
        -rw-r--r-- 1 MMooKow 197609 1859 Jul 27 10:52 FCC-SurveyForm.html
        -rw-r--r-- 1 MMooKow 197609 3847 Jul 27 10:52 FCC-TechnicalDoc.css
        -rw-r--r-- 1 MMooKow 197609 7045 Jul 27 10:52 FCC-TechnicalDoc.html
        -rw-r--r-- 1 MMooKow 197609 4493 Jul 27 10:52 FccProj.css
        -rw-r--r-- 1 MMooKow 197609 2493 Jul 27 10:52 FccProj.html
        -rw-r--r-- 1 MMooKow 197609   44 Jul 27 10:52 README.md
        ____________________________________
        First column represents file type and the persmissions it has.
        Second column represents number of memory blocks taken up by file or directory.
        Third column represents the file owner.
        Fourth column represents the group of the owner
        Fifth column represents the file size in bytes
        Sixth column represents the date and time when the file was created or modified last
        Seventh column represents file namme or directory

Sr.No.      Prefix & Description
1 -         Regular file, such as an ASCII text file, binary executable, or hard link.

2 b         Block special file. Block input/output device file such as a physical hard drive.

3 c         Character special file. Raw input/output device file such as a physical hard drive.

4 d         Directory file that contains a listing of other files and directories.

5 l         Symbolic link file. Links on any regular file.

6 p         Named pipe. A mechanism for interprocess communications.

7 s         Socket used for interprocess communication.

Metacharacters - special characters like ? and *. '?' matches a single character and '*' matched 0 or more characters. $ls ch*.doc matches all files that start with ch and end with .doc

Hidden files - Invisible files begin with the . character and are visible by adding -a to ls. .profile − The Bourne shell ( sh) initialization script

Vi editor - Can be used to create and edit files. Type `vi file_name` to open then press i to enter edit mode. Press esc to exit edit more then  ctrl + z + z to exit vi editor.

To move around a file in vi editor. Ensure you are not in edit more and press:

    l key to move to the right side.

    h key to move to the left side.

    k key to move upside in the file.

    j key to move downside in the file.

Display contents of a file name with `cat file_name`. Optional `-b` inbetween cat and file name displays line numbers.

Display word count with `wc file_name`.
    $ wc Week1Notes.md
    108  684 4662 Week1Notes.md

    First column - total number of lines in the file
    Second column - total number words in file
    Third column - total number bytes in file
    Fourth column - file name

Copy files with `cp source_file destination_file` ex: `cp filename copyfile`
Rename files with `mv old_file new_file` ex: `mv filename newfile`
Delete files with `rm filename` or `rm filename filename2 filename3` to delete multiples
    Best to use -i alone with rm to confirm you want to delete the file in question. `rm -i fileToDelte`.

Standard Unix streams:
    stdin - standard input (file descriptor 0). Unix program will read standard input from STDIN
    stdout - standard output (file descriptor 1). Unix program will write the default output at STDOUT
    stderr - standard error (file descriptor 2). Unix will write all error messages at STDERR

DIRECTORIES
reference following section: <https://www.tutorialspoint.com/unix/unix-directories.htm>

A directory if a file that other ordinary files, special files, or directory files are stored in. Files in Unix are stores as a tree and have a root node at / and all other directories are contained below it.

Home directory - The directory you enter when you log in to a Unix system. Can travel to with `cd ~` command. Can traverse to another users home directory with `cd ~username`
Return to last directory with `cd -`

Absolue/Relative path names - Directories area arranged in a tree with / (root) at the top. Parts of a path name are seperated by /. A pathname is absolute when  described in relation to root. Ex of absolute path names: /etc/passwd  |  /users/sjones/chem/notes  |  /dev/rdsk/Os3
Pathnames can also be relative to your working directory. / is excluded from the beginning of relative pathnames. Ex: chem/notes  |  personal/res

To print working directory `pwd`
Listing directories - use command `ls dirname` ex `$ls /usr/local`
Create directories - `mkdir dirname` ex: `$mkdir mydir`
    Directories can be created in other directories using `$mkdir /tmp/test-dir`. This example creates test-dir in the /temp directory. You can also create multiple directories by adding more than one to the end of the command `$mkdir docs pub`.

Creating parent directories - Sometimes when creating a directory it's parent directory(ies) might not exist. In those cases is -p with mkdir. `mkdir -p /tmp/amrood/test`.

Removing directories - use `rmdir dirname` command. When removing a directory mkae sure its EMPTY. Can also remove multiple directories in one command using spaces.

Change directories - use `cd dirname`. Can use absolute or relative directory paths
    Ex: `$cd /usr/local/bin` from here you can move to the /usr/home/amrood directory using the relative path `$cd ../../home/amrood`.

Renaming directories - `mv dirname newname` (move) command can be used to rename directoreis. Can also move a file to a new directory usin `mc filename dirpath`.

The directories . and .. - . represents the current directory you are working in and .. represents a directory one level above the current working directory.

FILE PERMISSION
reference following section: <https://www.tutorialspoint.com/unix/unix-file-permission.htm>

Every unix file has the following attributes:
    1. Owner permissions - determines what actions the owner can perform.
    2. Group permissions - determines what action the owner can perform.
    3. Other (world) permissions - determines what actions all other users can perform on the file.
The permissions indicator - While using the `ls -l` command various permission info is shown. 
    $ls -l /home/amrood
    -rwxr-xr--  1 amrood   users 1024  Nov 2 00:10  myfile
    drwxr-xr--- 1 amrood   users 1024  Nov 2 00:10  mydir

    Here, the first column represents different access modes, i.e., the permission associated with a file or a directory.

The permissions are broken into groups of threes, and each position in the group denotes a specific permission, in this order: read (r), write (w), execute (x) −

The first three characters (2-4) represent the permissions for the file's owner. For example, -rwxr-xr-- represents that the owner has read (r), write (w) and execute (x) permission.

The second group of three characters (5-7) consists of the permissions for the group to which the file belongs. For example, -rwxr-xr-- represents that the group has read (r) and execute (x) permission, but no write permission.

The last group of three characters (8-10) represents the permissions for everyone else. For example, -rwxr-xr-- represents that there is read (r) only permission.

File access modes - access modes are important to security.
    Read - ability to view the contents of a file.
    Write - ability to modify the contents of a file
    Execute - ability to run the file as a program

Directory access modes - Listed and organized the same as for any other file, however there are several differences.
    Read - Users can look at the contents and see the file names in a directory.
    Write - Users can add or delete files from a directory
    Execute - More like "traverse permission". A user needs execute access to the bin directory to execute the `ls` or `cd` commands.

Changing permissions - Use the `chmod` (change mode) command. 2 ways to use: symbolic and absolute. See website for details.

Changing owners and groups - When making an account on a Unix system it assigns an owner id and group id. 2 commans are available to change the owner and group of files.
    `chown` - changes owner
    `chgrp` - changed group
Changing ownership - `$ chown user filelist` the value of user can either be name of a user or user id (uid). Ex: `$ chown amrood testfile` changes owner of given file to amrood. Note - the super user/root has unrestricted access to change permissions. Other users can only change file they created.

Changing group ownership - `chgrp` is used to change group ownership. Ex: `$ chgrp special testfile`. changes group of the given file to special group.

SUID and SGID file permission - Set group id and set user id allow a program to change a users permission just for that program such as to change their password and then changes it back.
    The SUID and SGID bits will appear as the letter "s" if the permission is available. The SUID "s" bit will be located in the permission bits where the owners’ execute permission normally resides.

    For example, the command −

    `$ ls -l /usr/bin/passwd`
    `-r-sr-xr-x  1   root   bin  19031 Feb 7 13:47  /usr/bin/passwd*`

ENVIRONMENT
reference following section: <https://www.tutorialspoint.com/unix/unix-environment.htm>

An important concept in Unix is the environment, whish is defined b environment variables. These can be set by the system, shell, or any program and loads another program.
A variable is a caracter string to which a value is assigned. The vale can by a number, text, filename, device, or any other type of data.
Ex: first set variable TEST and then access it using the `echo` command.
    `$TEST="Unix Programming"`
    `$echo $TEST`

The .profile File - Maintained by the system admin. Can be customized but contains a minimum of the type of terminal you are using, a list of dirctories in which to locate commands, and a list of variables affecting the look and feel of your terminal.

Setting the terminal type - type of terminal is automatically configured by login or getty programs. Sometimes the autoconfig process guesses your terminal incorrectly. If your terminal is set incorrectly the output commands might look strange or you might not be able to interact with the shell properly. To avoid this most users set their terminal to the lowest setting using `TERM=vt100`

Setting the path - When typing a command in the command prompt the shell has to locate the command before it can be executed. The PATH var specifies the locations in which the shell should look for commands. Ususally it is set as follows: `$PATH=/bin:/usr/bin`

The PS1 and PS2 variables - The characters the shell displays as your command prompt are stored in the PS1 var. Changes can by made to this var to display differently. The changes are temporary unless you add PS1 to your .profile file. When you issue a command that is incomplete, the shell will display a seconday prompt and wait for you to complete the command and hit enter again. PS2 is the secondat prompt usual >. The PS2 var can be changed like the PS1 var using `$ PS2="secondary prompt->"`. A list of envornmental vars is available.

BASIC UTILITES
reference following section <https://www.tutorialspoint.com/unix/unix-basic-utilities.htm>
