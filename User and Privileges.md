# Users and Privileges

## File Permissions

![file_permissions](/IMAGES/file_permissions.png)

Here we can see the highlighted portion. This posrtion tells the user permissions for each file. Lets break the highlighted portion down:

`drwxr-xr-x`

Here:

- `d` denotes that the current folder is a directory
- `r` stands for read access
- `w` stands for write access
- `x` stands for execute access

### Permissions For Users

![user_permissions](/IMAGES/user_permissions.png)

Now lets see what our user (kali) and other user on this machine have permissions for the highligted folder called `Documents`

Reading from left to right we know that `d` stands for directory.

After that the permissions are listed. 

- The first permissions are of the owner of the file (which is in this case `kali`):

    `rwx` denotes that the `kali` user has **all three read, write and execute** permission on this directory

- After that we have the permission for the group users: 

    `r-x` meaning that the group user only has the **read and execute** permissions not the **write** permission

- Lastly we have the third settings for all users:

    `r-x` meaning that **both read and execute only** and no **write** access

## Granting Permissions Through The `chmod` Command

![chmod_part(1)](/IMAGES/chmod_command(1).png)

Here we have created a file named `hello.txt` through the `echo` command. On viewing the permissions we come to know that our current user and owner of this file has only **read and write but no execute permissions for this file**.

In order to change this permissions we use the `chmod` command. There are two ways of doing it:

- ###  Method 1: Symbolic Mode

    ![chmod_part(2)](/IMAGES/chmod_command(2).png)

    Here we used the following command syntax: `chmod +<permissions> <filename>`

- ### Method 2: Numeric Mode

    ![chmod_part(3)](/IMAGES/chmod_command(3).png)

    Here we have used the following command: `chmod <numeric_permissions> <filename>`

    Each permission (read, write, execute) is represented by a digit:

    - Read = 4

    - Write = 2

    - Execute = 1

    #### Example:

    For example:

    `chmod 755 hello.txt`

    This gives:

    - **Owner: read + write + execute (7)**

    - **Group: read + execute (5)**

    - **Others: read + execute (5)**

Below are the tables for easier understanding of these representations:

## 🔐 Permission Values Table

| Symbol | Permission | Binary | Value | Description                          |
|--------|------------|--------|-------|--------------------------------------|
| `r`    | Read       | 100    | 4     | View file contents / list directory  |
| `w`    | Write      | 010    | 2     | Modify file / create-delete in dir   |
| `x`    | Execute    | 001    | 1     | Run file as program / enter directory|
| `-`    | No perm    | 000    | 0     | No permission                        |

---

## 🔢 Numeric Permission Examples (for `chmod`)

| Command           | Owner | Group | Others | Meaning                                     |
|------------------|-------|-------|--------|---------------------------------------------|
| `chmod 777 file` | rwx   | rwx   | rwx    | Full access for everyone                    |
| `chmod 755 file` | rwx   | r-x   | r-x    | Owner full, others can read & execute       |
| `chmod 700 file` | rwx   | ---   | ---    | Only owner has full access                  |
| `chmod 644 file` | rw-   | r--   | r--    | Owner can read/write, others can only read  |
| `chmod 600 file` | rw-   | ---   | ---    | Only owner can read and write               |

## Adding A User

### Command

`sudo adduser <name>`

### Switching Users

`su <username>`

![adding_user](/IMAGES/adding_user.png)

Here we have created a user named John and switched from user `kali` to `john` using the `su` command

### `grep` Command

`grep "<word>" <filename/path>`

![grep_command](/IMAGES/grep.png)



