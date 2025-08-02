# Scripting With Bash

## Building A ping Sweeper With Bash Scripting

In this task we wanted to collect all ip addresses on our network by pinging them and storing them in a file. 

---

### Testing With ping Command

![test pinging the device](/IMAGES/bash_test_ping.png)

Next we create a fiel named ip.txt to store our ip addresses 

![creating ip.txt file](/IMAGES/creating_ip.txt.png)

Since we only want the ip addresses to be stored so we can use th e `grep` command to get that specific line. Combining with the `cut` command we can extract only the required ip address.

![Grabbing the ip address](/IMAGES/grabbing_the_ip.png)

Lets break down this command: `cat ip.txt | grep "64 bytes" | cut -d  " " -f 4 | tr -d ":" `

- `cat ip.txt`: Fetches the content of `ip.txt` file
- `|`: joins the commands together
- `grep "64 bytes"`: grabs the line containing "64 bytes" 
- `cut -d " " -f 4`: trims down the spaces between the words and `-f 4` tells to jump to the fourth word (which is in this case the ip address 192.168.248.128)
- `tr -d ":"`: trims the colon after the ip address

---

### Creating The Bash File

Now since we know how to grab an ip address through ping command we need to create a bash script to automate this and get all available ip addresses on the network

So we start by creating the file and opening it in mousepad using the command:

`mousepad ipsweep.sh`

![creating the file](/IMAGES/creating_ipsweep_bashfile.png)

So lets start with creating the script. The first part of every bash script is this line : `#!/bin/bash`

After that we start writing our code step by step:

- First we add that command which we used earlier to get the ip address:
    
    `ping 192.168.248.128 -c 1 | grep "64 bytes" | cut -d  " " -f 4 | tr -d ":"`

    ![Copying the command in newfile](/IMAGES/ipsweepfile(1).png)

- Since we know that we have a subnet mask of **255.255.255.0** so we only want to continously go through all 255 combination of the fourth portion of our IP address (192.168.248.128) i.e, `.128` part.

    So we modify the ip address in command and suppose a `variable` in its place (`$ip`).

    ![modifying the command](/IMAGES/ipsweepfile(2).png) 

- In order to itterate over this value we need a loop. We are going to use a for loop in this case which has the follwoing syntax:

    ```
    for $<variable_name> in `seq <range>; do
        <command to be repeated>
        done
        fi
    ```
    ![writing for loop](/IMAGES/ipsweepfile(3).png)

    Here `$ip` will:
        
    - Start from $ip = 1 
    - End at $ip = 254

    So the first address we will itterate over will be: `192.168.248.1`

    This will go on to change the value to **.2 , .3 ... upto .254** and end at the ip: `192.168.248.254`

- In order to make this more robust we change the hard coded first part of the ip address (network part) to take in user input

    ![taking in network part input](/IMAGES/ipsweepfile(4).png)

    Here we have replaced:
    
    - `192.168.248.` with `$1` (user input)

- In order to ensure that the user input is not empty we add the checking condition before the loop with an `if-else` statement

    ![adding if else block](/IMAGES/ipsweepfile(5).png)

- In order to speed up the process of looping we add an `&` at the and of the command:

    `ping -c 1 $1.$ip | grep "64 bytes | cut -d " " -f 4 | tr -d ":" &`

    ![speeding up the for loop](/IMAGES/ipsweepfile(6).png)

- Now hit `Ctrl + S` to save this file

---

### Running The Script

In order tp run a bash script we have the following syntax:

`./<filename>`

![running the file](/IMAGES/ipsweepfile(7).png)

---

#### Notes:

> A loop in programming is used to do the same task repeatedly 

> A variable is a value which we want to change as the program proceeds further. In its contrary if we want to make a vakue fixed we use a constant

> If - else block or ladder is used to check conditions in programming 
