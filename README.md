# Raspberrypi Env Initial 

## Initial your raspberrypi 
- Install the desired os with official image manager [Raspberry Pi Imager](https://www.raspberrypi.com/software/)
    - It support erase the microsd card and write your desired os image(raspberry pi os/ ubuntu/ debian/ )
- Ref:
    - https://www.youtube.com/watch?v=SjiVZ1QXBr0

## Methods to connect raspberrypi

### Use ethernet to connect with raspberrypi and use ssh to access
    1. buy a ethernet cable and adapter to connect to your computer
    2. construct the ssh dependencies on raspberrypi
        - we install ubuntu at the raspberry pi, so we reference the [post: Ubuntu Linux install OpenSSH server](https://www.cyberciti.biz/faq/ubuntu-linux-install-openssh-server/)
    3. (Mac) Open sharing with the Ethernet connection and check the local IP for raspberry pi
        - ref: [How to SSH into your Raspberry Pi with a Mac and Ethernet Cable](https://medium.com/@tzhenghao/how-to-ssh-into-your-raspberry-pi-with-a-mac-and-ethernet-cable-636a197d055) 
        - after use `ifconfig` to check the ip 
            ```
            $ ifconfig | grep inet
            ```
        - and we use `nmap` to scan the ip range: `$nmap -n -sP <Your IP Address>/24`
            ```
            $ nmap -n -sP 192.168.0.110/24
            ```
                - It would generate these info 
                    ```
                    Nmap scan report for 192.168.0.1
                    Host is up (0.013s latency).
                    Nmap scan report for 192.168.0.100
                    Host is up (0.016s latency).
                    Nmap scan report for 192.168.0.102
                    Host is up (0.015s latency).
                    Nmap scan report for 192.168.0.110
                    Host is up (0.00055s latency).
                    Nmap done: 256 IP addresses (4 hosts up) scanned in 20.99 seconds                    
                    ```
    4. Ｕse ssh command at terminal to connect
        ```
        #ssh <your_raspberry_pi_acccount>@<your_ip>
        $ssh weiren@192.168.0.100
        ```

### Resources
- [How To Connect Raspberry Pi To Macbook Pro?](https://www.comoapple.com/how-to-connect-raspberry-pi-to-macbook-pro.html)
