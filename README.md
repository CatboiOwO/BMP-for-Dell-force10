Hai everyone,

Here is instruktion how to use BMP is Dell force10 step by step.

I am using Windows 10 pro and gonna use Dell force10 4810 OS9

1. You need to download Tftpd64 or any alternative TFTP/DHCP server to host the boot files
   
⤷https://pjo2.github.io/tftpd64/



3. Make folder, example name "Dell"

4. In folder make .txt file or download "bmp-config.txt"



5. If you download jump to 5

File Name: bmp-config.txt

Copy this text and save

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


6. Go to network card settings and configure like that:
   
IPv4 Settings

Ip address: 192.168.100.1

subnet mask 255.255.255.0

Save



8. Now you need start Tftpd64

Click setting → DHCP and configure like that:











 ![image alt](https://github.com/CatboiOwO/OwO-BMP-for-Dell-force-10/blob/main/BMP-for-Dell-force-10%20photo/DHCP%20Ttpd64.PNG?raw=true) 


7. Go now to TFTP  (setting → TFTP)
8. 
   Click browse in base directory and navigate to your new folder from step 2.
   
   Configure the rest as shown in the photo.
 











 ![image alt](https://github.com/CatboiOwO/OwO-BMP-for-Dell-force-10/blob/main/BMP-for-Dell-force-10%20photo/Tftp%20Tftpd64.PNG?raw=true)

 8.Last step before start.
 
    Restart Tftpd64.
    
    Connect mgmt port in your swicth to your PC/Laptop. (Network card we configured before)
    
    Power on switch.
    
    If you go to Log Viewer and press Server Interface to 192.168.100.1 you gonna see that switch get ip and file via Tftp.










 ![image alt](https://github.com/CatboiOwO/OwO-BMP-for-Dell-force-10/blob/main/BMP-for-Dell-force-10%20photo/Logs%20Tftpd64.PNG?raw=true)

9. Wait for the switch to start up and load the initialization file.

11. 
    Now use putty and go to ssh.
    Port: 22
    Ip address: 192.168.100.10
    Username: admin
    Password: Your-Password

12. Enjoy your bmp.




