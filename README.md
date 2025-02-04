# Nmap-for-network-scaning
* Nmap for scanning networks to discover what hosts are present and what services are available on those hosts.
* Nmap's primary function is to scan a network and probe the hosts that it detects to determine the services running. It can scan using a number of techniques, which together can help identify services which are open to the Internet, that are closed, and those that are open, but behind a security filter of some sort.
# Task 1 Host discovery without doing a port scan
 Command --> $nmap -sn 192.168.XXX.XXX/24.
* Using the nmap -sn command on the target 192.168.XXX.XXX/24 will perform host discovery without doing a port scan. This means Nmap will attempt to determine which hosts are up and running within the specified IP range, which in this case is 192.168.XXX.XXX to 192.168.XXX.24
* By default, the -sn option sends a series of probes to detect hosts:
       1. An ICMP echo request
       2. A TCP SYN packet to port 443
       3. A TCP ACK packet to port 80
       4. An ICMP timestamp request
# Task 2 Perform a TCP SYN Ping scan   
command--> $nmap -PS 192.168.XXX.XXX
* Running the command nmap -PS 192.168.XXX.XXX will perform a TCP SYN Ping scan on the target IP address 192.168.XXX.XXX
* This scan sends a TCP SYN packet to the target to check if it is alive or responding. If the target responds with a SYN-ACK, it indicates that the host is up and listening on the port. If the target responds with an RST, it means the port is closed or the host is down.
* Here is a breakdown of the command:
 * 1.nmap: The network exploration and security auditing tool.
 * 2.PS: This option specifies the TCP SYN Ping scan.
 * 3.192.168.XXX.XXX: The target IP address to scan.
# Task 3 performs a UDP scan on the target IP
command --> $ nmap -sU 192.168.XXX.XXX
* -sU: This flag tells Nmap to perform a UDP scan.
# Task 4  Perform an UDP scan without sending a ping to determine if the host is up
command --> $ nmap -sU 192.168.XXX.XXX
* -P0: This flag tells Nmap to assume the target host is up and skip the initial ping step
# Task 5 perform a service version detection scan
command --> nmap -sV 192.168.XXX.XXX
* -sV: Enables service version detection
# Task 6 Perform os detection scan
command --> $ nmap -O 192.168.XXX.XXX
* -O: Enables Operating system detection
# Task 6 Perform a script scan on the IP
command --> $ nmap -sC 192.168.XXX.XXX
* -sC: This flag enables a script scan using the default set of scripts included with Nmap. It is equivalent to --script=default. These scripts are designed to gather more detailed information about the target, such as identifying vulnerabilities, checking for backup files, and testing default credentials.
# Task 7 Perform a service version detection scan on port 
command --> $ nmap -sV -p22 192.168.XXX.XXX
* The command nmap -sV -p22 192.168.XXX.XXX uses Nmap to perform a service version detection scan on port 22 of the IP address 192.168.XXX.XXX The -sV switch tells Nmap to attempt to determine the version of the service running on the specified port. The -p 22 switch specifies that only port 22 (commonly used for SSH) should be scanned.

  
