An IP (Internet Protocol) Address is the digital equivalent of a physical home address. While a MAC Address identifies the specific hardware (the "Social Security Number" of the machine), the IP Address identifies its current location on a network so that data knows where to go.

How an IP Address is Structured

There are two types of IP addresses in use today: IPv4 and IPv6.

1. IPv4 (The Standard)

This is the most common version. It consists of four numbers separated by periods, ranging from 0 to 255.

• Example: 192.168.1.15

• Technical Detail: It is a 32-bit address. Because there are only about 4.3 billion possible combinations, the world actually "ran out" of them, which is why we created IPv6.

2. IPv6 (The Future)

These are much longer and use both numbers and letters (hexadecimal).

• Example: 2001:0db8:85a3:0000:0000:8a2e:0370:7334

• Technical Detail: It is a 128-bit address, allowing for undecillions of unique addresses—enough for every grain of sand on earth to have its own IP.

How IP Works: The "Mailing" Process

To understand how it works "under the hood," imagine you are sending a letter from your house to a friend across the country.

Step 1: Encapsulation (The Envelope)

When you click "Send" on an email, your computer chops the data into small packets. It wraps each packet in an "envelope" called an IP Header.

• The Header contains: The Source IP (your address) and the Destination IP (the receiver's address).

Step 2: Routing (The Post Office)

Your computer sends the packet to your Default Gateway (your Router). The router doesn't know exactly where your friend's house is, but it knows which "highway" leads to the next major city. It looks at its Routing Table and passes the packet to the next router.

Step 3: Hopping (The Journey)

The packet "hops" from router to router across the WAN (Wide Area Network). Each router looks at the IP address and says, "This isn't for me, but I know it needs to go North," and passes it along.

Step 4: Reassembly (The Delivery)

Once the packets reach the destination IP, the receiving computer checks the Port Number (which we discussed earlier) to see which app the data belongs to (like Chrome or Spotify). It then puts the packets back in the correct order to recreate the original data.

Public vs. Private IPs: The "Apartment" Analogy

This is a crucial detail in how modern networking works.

• Public IP: This is the address assigned to your Router by your ISP. The entire world sees your house as this one single address.

• Private IP: Inside your house (LAN), your router gives a unique private IP to your phone, your laptop, and your TV (usually starting with 192.168...).

• NAT (Network Address Translation): This is the "Security Guard" in your router. When your laptop asks for a website, the router swaps your Private IP for the Public IP to send the request out. When the data comes back, the router remembers it was for your laptop and sends it to your private address.

Everything in [[Networking]]from your MAC address to an IP—is just a long string of 1s and 0s.

1. What is a Bit?

A Bit (short for Binary Digit) is the smallest unit of data in computing.

• It can only be one of two values: 0 (Off) or 1 (On).

• Think of it like a light switch.

When you group 8 bits together, you get a Byte.

• 1 Byte = 01011010 (8 bits)

2. What is Binary?

Binary is a "Base-2" counting system. Humans use "Base-10" (0–9). In binary, each position in an 8-bit byte represents a power of 2:
128 64 32 16 8 4 2 1

Why "0 to 255"?

In an IPv4 address (like 192.168.1.1), each of those four numbers is exactly one byte (8 bits).

• If all 8 bits are "Off" (00000000), the value is 0.

• If all 8 bits are "On" (11111111), you add up all the positions: 128 + 64 + 32 + 16 + 8 + 4 + 2 + 1 = 255.

This is why you will never see an IP address like 192.168.1.300. A single byte physically cannot hold a number higher than 255.

3. What is a MAC Address?

While the IP address is your "mailing address" (where you are), the MAC (Media Access Control) Address is your "Social Security Number" (who you are).

• It is Permanent: It is burned into the Network Interface Card (NIC) of your device at the factory.

• Format: It uses Hexadecimal (0–9 and A–F) instead of just numbers.

• Example: 00:1A:2B:3C:4D:5E

• Structure: * The first half identifies the Manufacturer (e.g., Apple, Intel, Samsung).

• The second half is the Unique Serial Number for that specific chip.

How they work together (The Detail)

When you send data on a LAN, your computer uses a process called ARP (Address Resolution Protocol) to link these two together.

1. IP Layer: Your computer says, "I want to send this to 192.168.1.50."

2. ARP Discovery: It shouts to the whole network, "Who has IP 192.168.1.50?"

3. The Target Responds: The target device says, "That's me! My MAC address is AA:BB:CC...."

4. MAC Layer: Your computer then wraps the data in a frame addressed to that specific MAC Address so the physical Switch knows which port to send the electricity to.


In [[Networking]], a Class is a way of slicing up the massive cake of 4.3 billion IPv4 addresses into manageable pieces.

When the internet was first designed, engineers created Classful Addressing to decide how many "Street Names" (Networks) vs. "House Numbers" (Hosts) a company could have.

The Three Main Classes

Remember, an IP address has four parts (octets), and each part goes from 0 to 255. The first number tells you which class the IP belongs to.

Class A: For the Giants

• Range: 1.0.0.0 to 126.0.0.0

• Design: 1 part for the Network, 3 parts for the Hosts.

• Scale: Very few networks, but each can have 16 million devices.

• Who uses it? Massive corporations (like Apple or IBM) and governments.

Class B: For Large Companies

• Range: 128.0.0.0 to 191.255.0.0

• Design: 2 parts for the Network, 2 parts for the Hosts.

• Scale: Medium amount of networks, each with 65,534 devices.

• Who uses it? Large universities and big businesses.

Class C: For You and Me

• Range: 192.0.0.0 to 223.255.255.0

• Design: 3 parts for the Network, 1 part for the Hosts.

• Scale: Millions of networks, but each only has 254 devices.

• Who uses it? Your home router and small offices.

How the "Work Detail" Works (The Binary)

The computer knows the class by looking at the very first Bits of the first byte:

• Class A: Always starts with a 0. (Binary: 0xxxxxxx)

• Class B: Always starts with 10. (Binary: 10xxxxxx)

• Class C: Always starts with 110. (Binary: 110xxxxx)

What is a "Private" Class?

You might notice your home IP usually starts with 192.168. This is a Private Class C address.

• These addresses are "non-routable," meaning they are invisible to the public internet.

• This allows millions of people to use the exact same address (192.168.1.1) inside their own homes without crashing the internet.

Why did we stop using Classes? (CIDR)

Classes were wasteful. If a company needed 300 IP addresses, they were too big for Class C (254) and had to take a Class B (65,000+), wasting thousands of addresses.

Today, we use CIDR (Classless Inter-Domain Routing). You’ll see it written as a slash at the end of an IP, like 192.168.1.1/24. This tells the computer exactly where the "Network" ends and the "Host" begins, down to the single bit.

To find the exact number of users (or "Hosts") in each class, we look at how many bits are left over for the host's address after the "Network" portion is taken out.

Each class has a set "Fixed" portion and a "Variable" portion.

1. Class A: The "Super-Network"

In Class A, the first byte (8 bits) is for the Network, and the remaining 3 bytes (24 bits) are for users.

• Math: 2^{24} = 16,777,216

• Usable Users: 16,777,214

• Why the -2? In every network, you cannot use the very first address (Network ID) or the very last address (Broadcast ID).

2. Class B: The "Large Business"

In Class B, the first two bytes are for the Network, leaving 2 bytes (16 bits) for users.

• Math: 2^{16} = 65,536

• Usable Users: 65,534

• Scale: This is perfect for a large university campus where thousands of students and faculty need unique IPs.

3. Class C: The "Home Office"

In Class C, the first three bytes are for the Network, leaving only 1 byte (8 bits) for users.

• Math: 2^{8} = 256

• Usable Users: 254

• Scale: This is why most home routers (like 192.168.1.x) can only handle 254 devices. If you try to connect the 255th device, the network is "full."

The "Work Detail": Why it's a Power of 2

Computers use binary, so every time you add 1 bit to the host portion, you double the number of users you can have.

• 7 bits = 128 users

• 8 bits = 256 users

• 9 bits = 512 users

A Note on Class D and E

You might notice the numbers jump from 223 to 224.

• Class D (224–239): Reserved for Multicasting (sending one stream of data to many people at once, like a live video stream). It doesn't have "users" in the traditional sense.

• Class E (240–255): Reserved for Experimental use and research.

The Subnet Mask is the secret key that tells a computer, "This part of the IP is the Network ID, and this part is the Host ID."

Without a mask, the computer wouldn't know if 192.168.1.1 is a Class A, B, or C address. It looks at the mask to "mask out" the network portion so it can see the specific user.

The Default Masks for Each Class

In binary, a 1 means "This is part of the Network" and a 0 means "This is part of the Host."

1. Class A Mask: 255.0.0.0

• Binary: 11111111.00000000.00000000.00000000

• Work Detail: Only the first number is locked for the network. The other three can be anything for the 16 million users.

2. Class B Mask: 255.255.0.0

• Binary: 11111111.11111111.00000000.00000000

• Work Detail: The first two numbers are locked. You have 65,534 spots left for users.

3. Class C Mask: 255.255.255.0

• Binary: 11111111.11111111.11111111.00000000

• Work Detail: The first three numbers are locked. You only have the last number (8 bits) to assign to your 254 users.

How the Computer "Thinks" (The ANDing Process)

When your computer wants to send data, it performs a mathematical operation called a Logical AND between its IP and its Subnet Mask.