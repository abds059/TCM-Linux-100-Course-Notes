# Navigating The File System

## User and Host Name

![User](/IMAGES/user.png)

Here we can see `viper@kali` in the terminal which denotes the following:

- `viper` is the user that we are using to log in with
- `kali` is our host name (name of the computer)

## Commands

- ### `cd` and `pwd` Commands

    - `cd` stands for **change directory**
    - ### Example Usage

    - **Moving inside another folder**

        - (`cd <folder-name>`)

        We here use the cd command to go inside the Downloads Folder from our current folder

        ![cd to move into a folder](/IMAGES/cd(1).png)

    - **Moving Backwards**

        - (`cd ..`)

        We can also use the cd command to go back one folder. Like we can go back from our downloads folder to our home/viper

        ![cd to move backwards](/IMAGES/cd(2).png) 

        The `pwd` command stands for **print working directory** and is used to display the current path that you are in at that moment

- ### `ls` Command

    - `ls` is used to list the folders and files inside a specific folder

        ![ls command](/IMAGES/ls.png)

        Here the different colors denote difference in files and folders and file types. For eg, the dark blue color shows the name of folders and the lighter ones are the name of files

    - `ls -la` command is used to display hidden files with the `.` prefix

        ![ls -la command](/IMAGES/ls%20la.png)

- ### `mkdir` and `rmdir` Commands

    - `mkdir` stand for **make directory**
    - `rmdir` stands for **remove directory**

        We are here going to create a directory named `hash`

        `mkdir <filename>`

        `rmdir <filename>`

        ![hash dir](/IMAGES/make%20dir.png)

        Later we use `rmdir` to remove the directory and ls confirms that the directory is no longer there

- ### `man` and `--help` Command

    - Both are used to what a command can do. They provide detailed guidance manual for a specific command

    - `man <command-name>`
    - `<command-name> --help`

        #### Output of man Command
        ![man command](/IMAGES/man-command.png)
        
        ![help command](/IMAGES/help-command.png)

- ### `echo` Command

    - Used to display back something back to the terminal
    - Also can be used to create a file

    - #### Displaying `"hi"` on the console

        ![echo-displayhi](/IMAGES/simple-echo.png)

    - #### Creating `new.txt` file 

        `echo 'some text' > <filename>`

        ![creating file through echo](/IMAGES/echo-createfile.png)

    - #### Removing `new.txt` file using `rm`

        `rm <filename>`

        ![rm new.txt file](/IMAGES/remove-file.png)

- ### `mv` Command

    - Used to move file completely from one location to another
    - `mv <filename> <destination>`

        ![move file](/IMAGES/move-file.png)

- ### `locate` Command

    - Used to locate a file by its name
    - `locate <filename>`

        First we used `sudo updatedb` so that we get the recent matches. Then we run `locate test.txt` command to locate the occurances of test.txt file.

        ![locate command](/IMAGES/locate-command.png)

- ### `passwd` Command

    - Used to change the user password

    - `passwd`

        Here I updated my default user (kali) password by the `passwd` command

        ![changing password](/IMAGES/changing-password.png)
