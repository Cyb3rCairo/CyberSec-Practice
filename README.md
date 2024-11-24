# CyberSec-Practice
This project is a hands-on exploration of Metasploitable 2, a purposely vulnerable virtual machine designed for cybersecurity practice. I used tools like Nmap and Metasploit to identify, exploit, and learn how to secure common vulnerabilities. It’s all documented step by step with images to help beginners (like me!) follow along and learn.

Reconnaissance Phase
Step 1: Verifying Connectivity with Ping
Before starting the exploitation process, it’s important to ensure that the target machine is reachable. I used the ping command to check the connectivity between my Kali Linux machine and the Metasploitable VM.

ping <192.168.3.130>
This command sends packets to the Metasploitable machine and confirms if the network connection is working. The expected result is a series of replies from the target machine, indicating successful connectivity.


![ping results](https://github.com/Cyb3rCairo/CyberSec-Practice/blob/main/pentest-images/1.%20ping-scan.png)

Step 2: Scanning Port 80 with Nmap and Service Version Detection
Once the target was reachable, I performed a more detailed scan of port 80 using the Nmap tool with the -sV option to detect service versions. This command helps identify what service is running on port 80 and its version, which can reveal potential vulnerabilities.

Explanation:

-sV: This flag tells Nmap to attempt to detect the version of the service running on the open port.
-p 80: Specifies that the scan should focus only on port 80.
Expected Output: The output will show the open port and the version of the service running on it (e.g., Apache). Here’s an example of what it might look like:


![ping results](https://github.com/Cyb3rCairo/CyberSec-Practice/blob/main/pentest-images/2.%20nmap-portscan.png)

Step 3: Opening Metasploit Console
After discovering that port 80 was open and running a version of Apache, I proceeded to open Metasploit to begin the exploitation phase. The msfconsole is the main interface used to interact with Metasploit’s modules and conduct attacks.

To open Metasploit, I used the following command:

msfconsole

This launches the Metasploit Framework, which provides access to numerous modules for penetration testing and exploitation.


![ping results](https://github.com/Cyb3rCairo/CyberSec-Practice/blob/main/pentest-images/3.%20metasploit.png)
