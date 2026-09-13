Hai everyone,
Here is instruktion how to use BMP is Dell force10.

I am using Windows 10 pro and gonna use Dell force10 4810 OS9

1. You need to download Tftpd64 or any alternative TFTP/DHCP server to host the boot files
⤷https://pjo2.github.io/tftpd64/

2. Make folder, example name "Dell"

3. In folder make .txt file or download "bmp-config.txt"

4. If you download jump to 5.
Copy this text and save
↓      ↓      ↓      ↓      ↓      ↓
────────────────────────────────────────────────────────────────
hostname S4810-1
username admin password Your-Password privilege 15
enable password Your-Password
interface ManagementEthernet 0/0
 ip address 192.168.100.10/24
 no shutdown
management route 0.0.0.0/0 192.168.100.1
ip ssh server enable
line vty 0 9
 password Your-Password
 login
────────────────────────────────────────────────────────────────
5.
Go to network card settings and configure like that:
IPv4 Settings
Ip address: 192.168.100.1
subnet mask 255.255.255.0
Save

6. Now you need start Tftpd64 
Click setting → DHCP and configure like that:
 ![image alt](https://github.com/CatboiOwO/OwO-BMP-for-Dell-force-10/blob/main/BMP-for-Dell-force-10%20photo/DHCP%20Ttpd64.PNG?raw=true) 









 ![image alt]() 
