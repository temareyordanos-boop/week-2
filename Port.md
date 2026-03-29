In networking, a port is a virtual point where network connections start and end. If you think of an IP address as the street address of a building (your computer), the ports are the specific apartment numbers or doors inside that building that direct traffic to the right place.

Without ports, your computer wouldn't know whether an incoming piece of data is meant for your web browser, your email app, or an online game.

How Ports Work

When data travels across a network, it uses a transport protocol—most commonly TCP (Transmission Control Protocol) or UDP (User Datagram Protocol). Each "packet" of data contains a port number to ensure it reaches the correct service.

• The IP Address: Gets the data to the right device.

• The Port Number: Gets the data to the right application on that device.

Essential Port Numbers to Know

If you are diving into networking, these are the "heavy hitters" you'll encounter most often:

• 20 & 21 (FTP): File Transfer Protocol; used for sending files between a client and a server.

• 22 (SSH): Secure Shell; used for secure remote logins to other computers.

• 25 (SMTP): Simple Mail Transfer Protocol; used for sending emails.

• 53 (DNS): Domain Name System; translates website names (https://www.google.com/search?q=google.com) into IP addresses.

• 80 (HTTP): The foundation of the World Wide Web (unsecured).

• 443 (HTTPS): The secure version of HTTP used by almost all modern websites.

Why are they important?

Ports are the backbone of network security. A Firewall works primarily by "opening" or "closing" these ports. For example, a web server will have port 80 and 443 open to the public, but it will likely keep port 22 (SSH) closed or restricted to prevent hackers from trying to log in remotely.

how the data actually gets delivered to those ports. Even if two applications use the same port number, they might handle data very differently depending on whether they use TCP or UDP.

Think of them as two different types of delivery services:

1. TCP (Transmission Control Protocol)

TCP is the "Reliable Delivery" service. It’s like a registered letter that requires a signature.

• The Handshake: Before sending data, the sender and receiver perform a "three-way handshake" to confirm both are ready.

• Error Checking: If a piece of data goes missing or arrives out of order, TCP asks the sender to re-transmit it.

• Best for: Web browsing (HTTP/HTTPS), Email (SMTP), and File Transfers (FTP). You wouldn't want a website to load with half the text missing!

2. UDP (User Datagram Protocol)

UDP is the "Fast Broadcast" service. It’s like a radio or TV broadcast; the data is sent out, and if you miss a second of it, the stream just keeps going.

• Connectionless: There is no handshake. The sender just starts "pouring" data toward the destination port.

• No Retries: If data is lost, it’s gone. UDP doesn't care about order or completeness; it only cares about speed.

• Best for: Live video streaming, online gaming, and VoIP (Voice over IP). In a game, you’d rather have a tiny bit of "lag" than have the entire screen freeze while the computer waits for a missing packet from five seconds ago.

TCP: The Phone Call (Reliable & Precise)

TCP is designed for accuracy. Before any real data is sent, the two computers "pick up the phone" and perform a three-way handshake:

1. Computer A: "Hey, can you hear me?"

2. Computer B: "Yes, I hear you! Can you hear me?"

3. Computer A: "Got you. I’m starting the transfer now."

Once the connection is live, TCP monitors every single piece of data (called a packet). If a packet gets lost in the mail or arrives out of order, TCP stops everything, asks for a "re-send," and puts the pieces back in the right order. This makes it slower because of the constant checking, but it is 100% reliable. You use this for things like web browsing, emails, and downloading files where every single letter and number must be perfect.

UDP: The Megaphone (Fast & Direct)

UDP is built for speed. It doesn't bother with a handshake or checking if the other side is listening. It just picks up a "megaphone" and starts shouting data as fast as possible.

There is no "Did you get that?" or "Let me repeat that." If a piece of data goes missing, it is simply gone forever. This makes it incredibly fast because there is no back-and-forth chatter to slow it down. You use this for things like live video calls or online gaming. If you’re playing a game and a packet of data is lost, you’d rather have a tiny "hiccup" or "lag" for a split second than have the entire game freeze while it waits for a missing piece of data from the past.

In Short

• TCP is like a conversationalist: It waits for a response, makes sure you understand, and fixes mistakes.

• UDP is like a broadcast: It sends the information out immediately and doesn't care if you missed a second of it.

**here are 30 of the most common and "well-known" ports used in networking, grouped by how they are typically used.**

Basic Web and Remote Access

• Port 80 (HTTP): The standard for unencrypted web traffic.  

• Port 443 (HTTPS): The secure, encrypted version of HTTP used by almost every modern website.  

• **Port 22 (SSH): Secure Shell; used for secure remote logins and managing servers.  

• **Port 23 (Telnet): An older, unencrypted way to log in to remote systems (rarely used now for security reasons).  

• Port 3389 (RDP): Remote Desktop Protocol; allows you to remotely control a Windows computer’s desktop.  

File Transfer and Sharing

• **Port 20 (FTP Data): Used by File Transfer Protocol to actually move the file data.  

• **Port 21 (FTP Control): Used to send commands (like "download" or "delete") to an FTP server.  

• Port 69 (TFTP): Trivial File Transfer Protocol; a very simple, "no-frills" way to send files, often used to boot up network devices.  

• Port 445 (SMB): Server Message Block; used by Windows for sharing files and printers over a local network.  

Email Services

• **Port 25 (SMTP): Used for routing email between mail servers.  

• Port 587 (SMTP Submission): The modern port used by email apps (like Outlook) to send mail to a server.

• Port 465 (SMTPS): An older port for secure email sending over SSL.  

• **Port 110 (POP3): Used by email apps to download messages from a server.  

• Port 995 (POP3S): The secure, encrypted version of POP3.  

• **Port 143 (IMAP): A more modern way to retrieve email that keeps messages synced across multiple devices.  

• Port 993 (IMAPS): The secure, encrypted version of IMAP.  

Infrastructure and Network Support

• Port 53 (DNS): Domain Name System; the "phonebook" of the internet that turns website names into IP addresses.  

• **Port 67 (DHCP Server): Used by servers to assign IP addresses to devices on a network.  

• **Port 68 (DHCP Client): Used by your device to request and receive that IP address.  

• Port 123 (NTP): Network Time Protocol; keeps your computer's clock perfectly synchronized with the rest of the world.  

• **Port 161 (SNMP): Simple Network Management Protocol; used by IT pros to monitor the health of routers and switches.  

• **Port 514 (Syslog): Used to send system logs and alerts to a central server for monitoring.  

Directory and Database Services

• **Port 389 (LDAP): Lightweight Directory Access Protocol; used for looking up users and passwords in a central directory.  

• Port 636 (LDAPS): The secure, encrypted version of LDAP.  

• Port 3306 (MySQL): The most common port for connecting to MySQL and MariaDB databases.  

• **Port 1433 (MSSQL): Used for connecting to Microsoft SQL Server databases.  

• Port 5432 (PostgreSQL): The default port for PostgreSQL databases.  

Miscellaneous Common Ports

• Port 5060/5061 (SIP): Used for setting up VoIP (internet phone) calls.

• Port 8080 (HTTP Alternate): Often used as a secondary port for web servers or proxy servers.  

• Port 1194 (OpenVPN): The default port used for creating secure VPN connections.  


Ports and vulnerabilities 

To give you a clear "note-style" explanation for all 30 ports, I’ve grouped them by their specific weaknesses. In a Real Attack, these are the technical flaws an attacker exploits to get inside.

**Remote Access & Management (High Risk)**

• Port 22 (SSH): Vulnerable to Brute Force attacks. Hackers use automated scripts to try millions of passwords to gain "Root" (total) control.
• Port 23 (Telnet): Vulnerable to Eavesdropping. It has no encryption, so passwords sent through it are visible to anyone on the network.
• Port 3389 (RDP): Vulnerable to Remote Code Execution (RCE). Famous bugs like "BlueKeep" allow hackers to take over a PC without a password.
• Port 161 (SNMP): Vulnerable to Information Disclosure. If the "community string" (password) is the default "public," an attacker can see your entire network map.

**Web & Proxy (Data Theft)**

• Port 80 (HTTP): Vulnerable to Cleartext Interception. Like Telnet, any data entered on a non-HTTPS site can be stolen.
• Port 443 (HTTPS): Generally secure, but vulnerable if the SSL/TLS certificate is old or misconfigured, allowing "Man-in-the-Middle" attacks.
• Port 8080 (HTTP Alternate): Often used for "Development" servers which usually have weaker security than the main website.

**File Sharing & Transfer (Malware Spreading)**

• Ports 20 & 21 (FTP): Vulnerable to Anonymous Login and "Bounce Attacks." Attackers can upload malicious files or steal sensitive documents easily.
• Port 69 (TFTP): Extremely vulnerable because it has no authentication. Anyone can request a file from this port if they know the filename.
• Port 445 (SMB): Vulnerable to Wormable Exploits. This is the primary way Ransomware (like WannaCry) spreads automatically from one computer to another.
• Port 1194 (OpenVPN): Vulnerable if the Encryption Keys are stolen or if the software version is outdated, allowing unauthorized network access.

**Email Services (Phishing & Identity)**

• Port 25 (SMTP): Vulnerable to Email Spoofing. Attackers use this to send "fake" emails that look like they came from your boss or your bank.
• Ports 465 & 587 (SMTPS): Vulnerable to Credential Stuffing, where leaked passwords from other sites are tested to break into your email.
• Ports 110 & 143 (POP3/IMAP): Vulnerable to Credential Sniffing if used without SSL. An attacker can read your private emails as they download.
• Ports 993 & 995 (IMAP/S & POP3/S): Secure versions of email, but still targets for Brute Force login attempts.

 **Directory & Databases (The "Gold Mine")**

• Port 389 (LDAP): Vulnerable to Injection. A hacker can send a crafted query to bypass the login and see the entire employee directory.
• Port 636 (LDAPS): The secure version of LDAP, but vulnerable to Certificate Spoofing if not managed correctly.
• Ports 3306 (MySQL), 1433 (MSSQL), 5432 (PostgreSQL): These are vulnerable to SQL Injection. An attacker uses these ports to "dump" the entire database, stealing usernames and credit card info.

**Infrastructure & Network (Redirection)**

• Port 53 (DNS): Vulnerable to Cache Poisoning. A hacker can redirect your web traffic to a fake version of a website (like a fake bank login).
• Ports 67 & 68 (DHCP): Vulnerable to DHCP Starvation. An attacker exhausts all IP addresses, crashing the network so no one can connect.
• Port 123 (NTP): Vulnerable to Reflection DDoS. Attackers use this port to "amplify" a small request into a massive flood of data to crash a server.
• Port 514 (Syslog): Vulnerable to Log Forgery. An attacker can send fake "All Clear" messages to hide the fact that they are currently breaking into the system.
• Ports 5060 & 5061 (SIP): Vulnerable to VoIP Hopping or "Toll Fraud," where attackers make expensive long-distance calls using your office phone system.

