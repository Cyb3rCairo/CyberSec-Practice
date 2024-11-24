# CyberSec-Practice
This project is a hands-on exploration of Metasploitable 2, a purposely vulnerable virtual machine designed for cybersecurity practice. I used tools like Nmap and Metasploit to identify, exploit, and learn how to secure common vulnerabilities. It’s all documented step by step with images to help beginners (like me!) follow along and learn.

Reconnaissance Phase
Step 1: Verifying Connectivity with Ping
Before starting the exploitation process, it’s important to ensure that the target machine is reachable. I used the ping command to check the connectivity between my Kali Linux machine and the Metasploitable VM.

ping 192.168.3.130
This command sends packets to the Metasploitable machine and confirms if the network connection is working. The expected result is a series of replies from the target machine, indicating successful connectivity.
![Nmap Scan Result](https://github.com/Cyb3rCairo/CyberSec-Practice/blob/main/pentest-images/1.%20ping-scan.png)
