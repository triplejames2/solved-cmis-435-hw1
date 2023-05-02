Download Link: https://assignmentchef.com/product/solved-cmis-435-hw1
<br>
This assignment will use data from a live UNIX host which is part of an autonomous system to illustrate layering. Use your book or google to help find the answers. (See attachment for better formatting)

First we will look at the host’s interfaces and the UNIX command to provide that data is netstat -i (network statistics for interfaces)

The data below was obtained:

[<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="f296958781869780b29f97809f9781">[email protected]</a> ~]$ netstat -I Kernel Interface table

Iface MTU Met RX-OK RX-ERR RX-DRP RX-OVR    TX-OK TX-ERR TX-DRP TX-OVR Flg

eth0       1500   0  3699939      0  83266      0   572363      0      0      0 BMRU lo        16436   0       88      0      0      0       88      0      0      0 LRU

<ol>

 <li>How many interfaces were displayed?      What are their names (actually logical addresses)</li>

 <li>. Does one of them appear to be a widely used LAN architecture? Yes If so which one?</li>

 <li>Assuming the following specification for the connectivity is 100baseTX, is this interface wired or wireless?</li>

 <li>What OSI layer would this connectivity designation reside on?</li>

 <li>. Because the internet is packet switched, which in part prevents one node from eating up all the bandwidth there is a limited the packet size, in the example above what is the maximum packet size for eth0?</li>

 <li>In the example above there are RX (received) and TX (transmit) values, therefore transmission in both directions simultaneously is possible, What is this called?</li>

 <li>How reliable is interface eth0 in both directions?</li>

 <li>. The standard for wired ethernet is IEEE 802.3, can you provide a wireless standard?</li>

</ol>

Second we will look at a sample IP packet which contains addressing and management information used in a layered approach.

[<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="e98d8e9c9a9d8c9ba9848c9b848c9a">[email protected]</a> ~]$ sudo tcpdump ip -e -vvv -c5 -n tcpdump: listening on eth0, link-type EN10MB (Ethernet), capture size 65535 bytes 14:41:06.253591 ea:e4:2e:b6:ce:8a &gt; 82:c1:f4:de:1b:72, ethertype IPv4 (0x0800), length 670: (tos 0x0, ttl 64, id 29527, offset 0, flags [DF], proto TCP (6), length 656)10.0.1.11.39335 &gt; 10.0.1.4.ldap: Flags [P.], cksum 0x1891 (incorrect -&gt; 0x8ce8), seq 2621924776:2621925380, ack 3220579564, win 501, options [nop,nop,TS val 616048594 ecr 1551064829], length 604 14:41:06.255253 82:c1:f4:de:1b:72 &gt; ea:e4:2e:b6:ce:8a, ethertype IPv4 (0x0800), length 181: (tos 0x0, ttl 64, id 24762, offset 0, flags [DF], proto TCP (6), length 167)10.0.1.4.ldap &gt; 10.0.1.11.39335: Flags [P.], cksum 0x3fc0 (correct), seq 1:116, ack 604, win 1002, options [nop,nop,TS val 1551091309 ecr 616048594], length 115 14:41:06.255285 ea:e4:2e:b6:ce:8a &gt; 82:c1:f4:de:1b:72, ethertype IPv4 (0x0800), length 66: (tos 0x0, ttl 64, id 29528, offset 0, flags [DF], proto TCP (6), length 52)10.0.1.11.39335 &gt; 10.0.1.4.ldap: Flags [.], cksum 0x1635 (incorrect -&gt; 0x6a7f), seq 604, ack 116, win 501, options [nop,nop,TS val 616048595 ecr 1551091309], length 0 14:41:06.256641 ea:e4:2e:b6:ce:8a &gt; 00:00:5e:00:01:03, ethertype IPv4 (0x0800), length 1226: (tos 0x10, ttl 64, id 20783, offset 0, flags [DF], proto TCP (6), length 1212)10.0.1.11.ssh &gt; 64.83.217.120.bim-pem: Flags [P.], cksum 0x2985 (incorrect -&gt; 0xd7a5), seq 2503743393:2503744565, ack 376061211, win 21976, length 1172 14:41:06.257581 ea:e4:2e:b6:ce:8a &gt; 00:00:5e:00:01:03, ethertype IPv4 (0x0800), length 426: (tos 0x10, ttl 64, id 20784, offset 0, flags [DF], proto TCP (6), length 412)10.0.1.11.ssh &gt; 64.83.217.120.bim-pem: Flags [P.], cksum 0x2665 (incorrect -&gt; 0xdbab), seq 1172:1544, ack 1, win 21976, length 372 5 packets captured 5 packets received by filter 0 packets dropped by kernel1. To uniquely identify each packet a time stamp is provided. What time did the first packet arrive?

2. After the time stamp the MAC (media access control) addresses appear, the source and the destination separated by a &gt;. They are often referred to as a physical address, what OSI layer are they really on?

3. The MAC addresses are represented by 12 hexadecimal characters, so how many bit addresses are they?

What is max address space?

4. Given the above what LAN architecture is being used in the data link layer?How are MAC address assigned in ethernet?

5. What version of IP is being used on the network layer?

6. What is the length of the first data packet? Based on the sample above are variable packet sizes supported? How do variable length packets improve efficiency?

7. In the last packet above tos (type of service) (which is a measure of quality of service) is set at 10 hex which equals 00010000, using goggle can you find the meaning of this switch being turned on?

8. In the first packet the ttl (time to live) is set at 64, what does this mean? What layer does ttl reside on?

9. OSI layer 4 is the transport layer, which layer 4 protocol is being used in packet 1?

10. The source net.node.port address in packet 1 is 10.0.1.11.39335, where 10 is the net, 0.1.11 the node and 39335 is the port, on which OSI layers do net, node and port reside?

11. In the first packet the checksum is incorrect. What is the purpose of the checksum?Is there a problem with it being incorrect?