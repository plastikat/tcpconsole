Installation:
------------
make install

sysvinit users need to do:
	Add to /etc/inittab:
	tc:12345:respawn:/usr/local/sbin/tcpconsole

	Send HUP to init:
	killall -HUP init

Systemd users need to do:
        systemctl enable tcpconsole
        systemctl start tcpconsole

This program only works on Linux.

To connect to the tcpconsole, telnet to port 4095.

Please make sure that port 4095 is firewalled from networks that should not be able to connect, e.g. the internet: it should only be connectable from your management LAN.

You need to create a file /etc/tcpconsole.pw (rw-------, or chmod 600 /etc/tcpconsole.pw) containing the login password.


Comments, send them to: mail@vanheusden.com
