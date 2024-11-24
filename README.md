# CyberSec-Practice
This project is a hands-on exploration of Metasploitable 2, a purposely vulnerable virtual machine designed for cybersecurity practice. I used tools like Nmap and Metasploit to identify, exploit, and learn how to secure common vulnerabilities. It’s all documented step by step with images to help beginners (like me!) follow along and learn.

Reconnaissance Phase
**Step 1: Verifying Connectivity with Ping**
Before starting the exploitation process, it’s important to ensure that the target machine is reachable. I used the ping command to check the connectivity between my Kali Linux machine and the Metasploitable VM.

**ping <192.168.3.130>**

This command sends packets to the Metasploitable machine and confirms if the network connection is working. The expected result is a series of replies from the target machine, indicating successful connectivity.


![ping results](https://github.com/Cyb3rCairo/CyberSec-Practice/blob/main/pentest-images/1.%20ping-scan.png)

**Step 2: Scanning Port 80 with Nmap and Service Version Detection**
Once the target was reachable, I performed a more detailed scan of port 80 using the Nmap tool with the -sV option to detect service versions. This command helps identify what service is running on port 80 and its version, which can reveal potential vulnerabilities.

Explanation:

-sV: This flag tells Nmap to attempt to detect the version of the service running on the open port.
-p 80: Specifies that the scan should focus only on port 80.
Expected Output: The output will show the open port and the version of the service running on it (e.g., Apache). Here’s an example of what it might look like:


![results](https://github.com/Cyb3rCairo/CyberSec-Practice/blob/main/pentest-images/2.%20nmap-portscan.png)

**Step 3: Opening Metasploit Console**
After discovering that port 80 was open and running a version of Apache, I proceeded to open Metasploit to begin the exploitation phase. The msfconsole is the main interface used to interact with Metasploit’s modules and conduct attacks.

To open Metasploit, I used the following command:

**msfconsole**

This launches the Metasploit Framework, which provides access to numerous modules for penetration testing and exploitation.


![results](https://github.com/Cyb3rCairo/CyberSec-Practice/blob/main/pentest-images/3.%20metasploit.png)

**Step 4: Searching for HTTP Version Exploits and Selecting the Exploit**
Inside Metasploit, I searched for potential exploits related to the HTTP service using the following command:

**search http_version**
This search showed available exploits related to HTTP services, and I selected the first one (ID: 0) from the list.

After selecting the exploit, I used the following command to load it:
**use 0**

Then, I displayed the available options for configuring the exploit using:

**show options**
This command displayed the required and optional parameters, such as the RHOSTS (target IP address) and RPORT (target port), which I needed to configure in order to proceed.

![results](https://github.com/Cyb3rCairo/CyberSec-Practice/blob/main/pentest-images/4.%20metasploit1.png)

At this point, I configured the RHOSTS parameter to the target IP address (e.g., 192.168.3.130) and other relevant options.

![results](https://github.com/Cyb3rCairo/CyberSec-Practice/blob/main/pentest-images/5.%20metasploit2.png)

**Step 5: Running the Exploit**
Once the exploit was properly configured, I executed it by using the run command inside Metasploit:

**run**
This command attempted to exploit the vulnerability and gain access to the target machine.

**Step 6: Accessing the Target Website**
After running the exploit, I successfully accessed the target website by navigating to:

**http://192.168.3.130/phpinfo.php**
This page showed detailed information about the PHP configuration on the server, which confirmed that I had successfully exploited the vulnerability and gained access to the target system.


![results](https://github.com/Cyb3rCairo/CyberSec-Practice/blob/main/pentest-images/6.%20php%201.png)

**Step 7: Searching for PHP CGI Exploits**
Next, I searched for more specific exploits related to PHP CGI. I used the following command in Metasploit:

**search php_cgi**
This search returned relevant exploits for vulnerabilities in PHP CGI configurations, and I could use these to further explore or exploit the target system.

![results](https://github.com/Cyb3rCairo/CyberSec-Practice/blob/main/pentest-images/7.%20target.png)

![results](https://github.com/Cyb3rCairo/CyberSec-Practice/blob/main/pentest-images/8.%20target2.png)

After identifying the PHP CGI Argument Injection exploit, I selected it for use by entering:

**use exploit/linux/http/php_cgi_arg_injection**
Once I selected the exploit, I reviewed the available options using:

**show options**

This displayed the parameters I needed to configure for the attack. Specifically, I set the RHOSTS to the target IP (192.168.3.130), as well as other relevant settings like the RPORT.

After configuring the options, I ran the exploit by executing the following command:

**exploit**
This command triggered the exploitation of the PHP CGI Argument Injection vulnerability, which may have allowed me to execute commands or gain further access to the target machine.

![results](https://github.com/Cyb3rCairo/CyberSec-Practice/blob/main/pentest-images/9.%20exploit.png)

![results](https://github.com/Cyb3rCairo/CyberSec-Practice/blob/main/pentest-images/10.%20archives.png)




