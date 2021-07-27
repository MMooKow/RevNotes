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
