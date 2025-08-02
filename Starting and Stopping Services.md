# Starting and Stopping Services

## Running A Server

If we want to share our files with someone we can run a server from our terminal using `service` command. There are two ways listed here to do this:

- ### Running An Apache Server
    For this we are running appache2 server using the command:

    `sudo service apache2 start`

    This will start a server on the device ip address which can be accessible from Firefox

    We can stop the server by the following command:

    `sudo service apache2 stop`

    ![apache2 start and stop](/IMAGES/apche2_startandstop.png)

    ![firefox apache2](/IMAGES/apche2_webserver.png)

- ### Running Server Through Python

    In order to run the server we are going to use the following command:

    `python -m http.server <port_number>`

    ![python server start and stop](/IMAGES/pythonserver_startandstop.png)

    ![python web server firefox](/IMAGES/python_server_web.png)


## systemctl Command

This command is used to enable or disable services or applications to start on boot.

`sudo systemctl enable/disable <service_name>`

![systemctl enable/disable ssh](/IMAGES/systemctl_command.png)



