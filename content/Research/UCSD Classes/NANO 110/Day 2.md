#### Terminal Commands for This Class
ssh fdininno@login.expanse.sdsc.edu
pwd: 6M@rTsD@@@a4yW
port: 22

#### Bash Information
Permissions: r, w, x = read, write, execute
These will appear under information about the owner, group, and all.
ASCII example: rw-r--r--
Bitmap example: 110-100-100 (6-4-4 in digital, 6-4-4 in octal)
You will want to set your files so that only the owner will be able to execute it.

Example of an execution: 
`$ ll pw.x
`-rwxr-xr-x 1 root root 9663773 Sep 3 2014 pw.x

- The `-` represents that it is a regular file (not a separator)
- The permissions for the owner are the following three characters `rwx`
- The permissions for the group are the next three characters `r-x`
- The permissions for everyone are the next three characters `r-x`

You have to be able to change the permissions
`$ chmod 770 1.sh`
This will change the `l.sh` file to be `rwx` for the owner and group, but no permissions for everyone else.

You also have to print the working directory. Use `pwd`
Make a folder (or change to) `nano110`

You also have to make this folder: `/expanse/lustre/scratch/key021/`

#### Some handy `ls` commands
- `-l` "long" format shows file details
- `-a` shows hidden files
- `-t` sort by latest modified
- `-r` reverse order of default sorting
- `-S` sort by size
- `-R` list recursively, showing subdirectories
- `-i` shows the index number of each file, called the inode
- `-g` shows group ownership of files
- `-h` print size files in human-readable format
- `-d` list the directory rather than the content

