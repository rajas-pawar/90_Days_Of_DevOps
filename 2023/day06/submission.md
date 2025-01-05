# 📁 Understanding Linux File Permissions: The Building Blocks
![image](https://github.com/user-attachments/assets/7d49ba8e-d2b3-4abd-80ac-856ba418e4ad)

- 🎭 The Three Permission Types:

```
r (Read) 👀   - Can look but cant touch
w (Write) ✍️   - Can modify and delete
x (Execute) 🚀 - Can run the file
```

- 👥 The Three User Categories:
```
Owner 👑  - The VIP (usually you or the creating process)
Group 👥  - The guest list (team members)
Others 🌍 - Everyone else
```

- 🔍 Real-World Example Time!
Let's say you're managing a web development team's project:
```
$ ls -ltr
drwxr-x--- 3 sarah developers 4096 Jan 6 10:00 project_source/
-rw-r----- 1 sarah developers  123 Jan 6 10:01 config.json
-rwx------ 1 sarah developers  256 Jan 6 10:02 deploy.sh
```
Let's break this down:

project_source/ is a directory, and sarah (the owner) has full access, while the group has read and execute permissions. Others have no access.

config.json is a file where the owner can read/write, the group can only read, and others have no access.

deploy.sh is an executable script file where only the owner (sarah) has full access (read, write, execute). No one else can access it.


# 🚀 Access Control Lists (ACLs)

Access Control Lists (ACLs) provide extra flexibility for setting permissions on files and directories in a file system. ACLs allow specifying access rights for individual users or groups, beyond the basic owner-group-others scheme.

- Use of ACLs :

Imagine you need to grant specific read or write access to a user who is not part of your group. Without adding the user to the group, you can use ACLs to grant the required permissions.

- Commands:

— getfacl

Used to view the ACLs of a file or directory.

Displays standard permissions (rwx) along with additional ACL entries.

Syntax:
```
getfacl <filename>
```
— setfacl

Used to modify or set ACLs for a file or directory.

Can add, modify, or remove permissions for specific users or groups.

Syntax:
```
setfacl -m u:<username>:<permissions> <filename>  # Add/Modify user permissions
setfacl -m g:<groupname>:<permissions> <filename> # Add/Modify group permissions
setfacl -x u:<username> <filename>                # Remove ACL for a user
setfacl -b <filename>                             # Remove all ACLs
```

Note :

- Why We Use -R:

To avoid applying commands individually to each file and subdirectory.
It simplifies tasks when working with directories that contain many nested files and folders.



# 🫡 Conclusion

Understanding file permissions and ACLs is crucial for maintaining the security and proper functioning of a Linux system. File permissions regulate basic access rights, while ACLs offer more granular control, allowing precise access settings for individual users and groups.
