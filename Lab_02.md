* `adduser testUser` - Add a new user to the system.
* `passwd testUser` - Set password for the user.

* `su testUser` - Switch to testUser.

* `cat file.txt` - Show the content of a file.
    * `cat > file.txt` - write to a file by taking input from STDIN.
    * `cat file1.txt > file2.txt` - Copy the content of file1.txt to file2.txt.
    * `cat file1.txt >> file2.txt` - Append the content of file1.txt to file2.txt.
    * `cat file1.txt file2.txt > file3.txt` - Merge the content of file1.txt & file2.txt to file3.txt.

* `echo $OLDPWD` - print the previous working directory
* `printenv` - print all environment variables
* `whereis bash` - Show binary, source, and manual page files for a command.
* `which bash` - Show the path of the executable program.
