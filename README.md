# Use-Linux-commands-to-manage-file-permissions
Use Linux commands to manage file permissions

# File permissions in Linux

## Project description

* Examine existing permissions on the file system.   
* Determine if the permissions match the authorization that should be given.   
* If they do not match, modify the permissions to authorize the appropriate users and remove any unauthorized access.

## Check file and directory details

![][image1]  
The /home/researcher2/projects directory and the permissions of the files and subdirectory it contains.  
Files:

* project\_k.txt \-rw-rw-rw-  
  * User \= read, write,  
  * Group \= read, write  
  * Other \= read, write  
* project\_m.txt \-rw-r-----  
  * User \= read, write  
  * Group \= read  
  * Other \= none  
* project\_r.txt \-rw-rw-r--  
  * User= read, write  
  * Group \= read, write  
  * Other \= read  
* project\_t.txt \-rw-rw-r--  
  * User \= read, write  
  * Group \= read, write  
  * Other \= read  
* .project\_x.txt \-rw-w---  
  * User \= read, write  
  * Group \= write  
  * Other \= none

There is also one subdirectory inside the projects directory named drafts. The permissions  
on drafts are:   
drafts drwx--x---

* User \= read, write, execute  
* Group \= execute  
* Other \= none

## Describe the permissions string

The permissions string is a 10-character string that indicates the permission assignments for the contents of a directory. It will indicate whether it is a file or directory, then the read, write, and executable permissions for the user, the group, and others.

* First character: A dash (-) indicates a regular file, while a letter "d" indicates a directory   
* Second through fourth characters: The permissions for the user, who owns the file   
* Fifth through seventh characters: The permissions for the group that owns the file   
* Eighth through tenth characters: The permissions for all other users 

## Change file permissions

Changed the permissions of the project\_k.txt file so that the owner type of other doesn’t have write permissions.

![][image2]

## Change file permissions on a hidden file

The file .project\_x.txt is a hidden file that has been archived and should not be written to by others. The user and group should still be able to read this file.  
Changed the permissions of the file .project\_x.txt so that both the user and the group can read, but not write to, the file.

![][image3]

## Change directory permissions

Only researcher2 user should be allowed to access the drafts directory and its contents.  
Removed the execute permission for the group from the drafts directory.

![][image4]

## Summary

Using the chmod and the ls \-la commands, I was able to successfully demonstrate the ability to modify permissions of files and directories in Linux.  
