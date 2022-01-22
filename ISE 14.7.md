# Xilinx ISE Design Suite

## No-cost editions of ISE
Both WebPack and Embedded Edition can be installed free of charge, but require a node-locked license
The license file uses the MAC address of the eth0 interface which doesn't exist on modern Linux,
but can be added with the following commands:
> sudo ip link add eth0 type dummy
> sudo ifconfig eth0 hw ether xx:xx:xx:xx:xx:xx up
where the xx is replaced with a suitable MAC address.
Embedded edition supports the high-end Kintex chip used on one of the QMTech boards.

## Libraries required that won't be installed as standard on modern distros
libncurses version 5 is needed by planahead.
libqtnetwork is required for the Xilinx License Configuration Manager but missing from the installation package - it can be downloaded at
[https://support.xilinx.com/s/article/58400?language=en_US](https://support.xilinx.com/s/article/58400?language=en_US)

## Connecting to the USB Platform cable
Impact tries to use a kernel module driver for the USB platform cable by default.  It hasn't been possible to build this module against a modern kernel for many years.
A libusb-based userspace driver can be found at [http://www.rmdir.de/~michael/xilinx/](http://www.rmdir.de/~michael/xilinx/)
and mirrored at [https://github.com/JohnDMcMaster/xilinx-usb-driver](https://github.com/JohnDMcMaster/xilinx-usb-driver)
(The news section on that page suggests that this userspace driver should no longer be needed since ISE was adapted to ship first with a userspace driver which can be enabled with an environment variable, and then to using the userspace driver by default.  I haven't managed to get impact from ISE 14.7 to work without using the replacement driver, however.)

