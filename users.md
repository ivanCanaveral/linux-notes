# Users

## /etc/passw file

Stores users, user ID number (UID), user's group ID number (GID), fullname, home directory and login shell (`/bin/bash` by default)

## /etc/groups file

Stores groups and group ids.

## Permissions

```
-rwxr-xr-x 1 pi pi 857854932 Aug  3 06:23 myfile.txt
```

The first dash (-) indicates the type of filei: d for directory, s for special file, - for a regular file. The next (in groups of three):
* owner’s permission x to the file 
* permissions for the members of the same group as the file owner 
* permissions for all other users

### Create users

`useradd <name>`

Use `-d <dir>` to specify the user's home dir, `-s /bin/<shell>` to define a shell, or `-e <YYYY-MM-DD>` to fix an expiration date.

(*) New users can change their password using the `passwd` command.

### Groups

* `newgrp <groupname>` log in to a new group
* `chgrp <groupname>` change group ownership

### chmod command

```
chmod u+r,g+x <filename/folder>
```

* __u__ is for user
* __r__ is for read
* __g__ is for group
* __x__ is for execute


```
chmod 444 <filename/folder>
```

| 7 | r | w | x |
|---|---|---|---|
| 6 | r | w | - |
| 5 | r | - | x |
| 4 | r | - | - |
| 3 | - | w | x |
| 2 | - | w | - |
| 1 | - | - | x |
| 0 | - | - | - |

### chown command

All files are “owned” by the user who creates them and by that user’s default group. To change the ownership to a specific user and group:

```
chown user:group /path/to/file
```

Use `chown -R user:group path` to do it in a recursive way.
