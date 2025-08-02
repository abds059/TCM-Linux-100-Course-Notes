# Common Network Commands

## `ip a` Command

- Used to list down the ip address of the device
- We can also use `ifconfig`

![ifconfig command](/IMAGES/ifconfig_command.png)

![ip a command](/IMAGES/ip-a_command.png)

Here we can note down the following things:

- **IPV4 Address: 192.168.138.140**
- **Subnet Mask: /24 => (255.255.255.0)**
- **MAC Address: 00:0c:29:60:7d:fb**
- **IPV6 Address: fe80::20c:29ff:fe60:7dfb**

## `arp` Command

- Used to map ip addresses to their relevant MAC addresses

    `arp -a`

- We can also use `ip n`

    ![arp and ip n commands](/IMAGES/arp_ipn.png)

## `ip r` Command

- Help us to look at the **Routing Table**

    ![ip r command](/IMAGES/ip_r_command.png)

## `ping` Command

- Used to send packets to a destination device to check connectivity

    `ping <ip address>`

    ![ping command](/IMAGES/ping_command.png)

    Here we have pinged one of the public ip of google **(8.8.8.8)**

