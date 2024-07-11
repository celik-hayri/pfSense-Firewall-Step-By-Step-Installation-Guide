# pfSense-Firewall-Step-By-Step-Installation-Guide

This project demonstrates the installation and configuration of pfSense firewall on a VirtualBox virtual machine. The steps include downloading the pfSense ISO file, setting up the virtual machine, installing pfSense, and performing initial and GUI configurations. This guide is intended for educational purposes and to help others set up their own pfSense firewall.


## Downloading pfSense ISO File

1. Navigate to the pfSense download page on archive.org:
   - [pfSense-CE-iso-2.7.2-RELEASE-amd64](https://archive.org/details/pfSense-CE-iso-2.7.2-RELEASE-amd64)
2. Download the GZIP file from the specified folder.

## Adding pfSense to VirtualBox and Configuring Settings

1. Open VirtualBox and add a new machine.
2. Name the machine, choose the ISO file, select `BSD` as the type, and `FreeBSD (64-bit)` as the version.
3. Allocate 1024 MB of memory and assign 2 processors.
4. Create a virtual hard drive with 16 GB of storage and proceed to the next step.
5. Review the settings and click `Finish`.
6. Select your pfSense virtual machine and click `Settings`.
7. In the `System` settings, untick `Floppy`.
8. In the `Audio` settings, untick `Enable Audio`.
9. In the `USB` settings, untick `Enable USB Controller`.
10. Configure network adapters as follows:
    - Adapter 1: NAT
    - Adapter 2: Host-only Adapter
    - Adapter 3: Internal Network
    - Adapter 4: Internal Network

## Starting and Configuring pfSense

1. Start the pfSense virtual machine.
2. Follow the on-screen instructions and hit `Enter` to continue.
3. Select the option shown in the picture and hit `Enter`.
4. Choose `Guided Root-on-ZFS` and hit `Enter`.
5. Continue hitting `Enter` to proceed with default options.
6. Select `VBOX HARDDISK` by hitting the space bar and then `Enter`.
7. Choose `Yes` and wait for the installation to complete.
8. Reboot the virtual machine.
9. Remove the installation disk and force the removal if necessary.
10. Reset the virtual machine.
11. Choose `No` for manual configuration and hit `Enter`.
12. Assign network interfaces:
    - WAN: `vtnet0` (NAT Network)
    - LAN: `vtnet1` (Host-only Adapter)
    - OPT1: `vtnet2` (Internal Network 1)
    - OPT2: `vtnet3` (Internal Network 2)
13. Proceed by hitting `Y` and `Enter`.
14. Set IP addresses for interfaces:
    - LAN: Enter your desired IP address and subnet mask.
    - Configure DHCP for LAN with a starting and ending IP range.
    - Choose `No` for IPv6 configuration.
15. Repeat the process for optional interfaces (OPT1 and OPT2).

## GUI Configurations

1. Select the virtual machine (e.g., Kali Linux) and attach it to the internal network.
2. Check the IP address assigned to the machine.
3. Access the pfSense web interface by navigating to the IP address.
4. Click `Advanced` and `Accept the Risk and Continue`.
5. Log in with the default credentials:
    - Username: `admin`
    - Password: `pfsense`
6. Follow the setup wizard:
    - General Information: Fill in details and untick `Override DNS`.
    - Time Zone: Set your preferred time zone.
    - WAN Configuration: Untick `Block RFC1918 Private Networks`.
    - Set a new password for the admin account.
7. Reload and finish the setup.
8. Customize the dashboard by adding widgets and configuring firewall rules as needed.

---

## Conclusion

This guide provides a step-by-step walkthrough for setting up a pfSense firewall on VirtualBox. By following these instructions, you can configure a robust firewall to enhance your network security. For further customization and advanced configurations, refer to the official pfSense documentation.

`## NOTE:`

- `Each folder of pictures is self-explanatory`
- `Every picture includes a description`
- `Descriptions provide information on what to do`
- `Important parts are highlighted in red in every picture`

`Good Luck!`
