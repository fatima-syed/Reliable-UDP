# Reliable-Badnet
The objective is to transfer a file from a client to a server's local directory using a client/server pair. The communication between them should take place via UDP on an extremely unreliable network, and the primary aim is to ensure the successful delivery of files despite the network's unreliability.

In particular, this network has a tendency to:

◆ Drop packets<br>
◆ Duplicate packets<br>
◆ Introduce bit errors within packets (only one bit error)<br>
◆ Deliver packets out of order<br>

## Badnets
There are six Python classes that are available for you to test. Each class incorporates one or more BadNet behaviors. Here are the details of each class:

**BadNet0:** This class doesn't cause any packet drop, duplication, or errors. It can be considered a "GoodNet."<br>
**BadNet1:** This class drops every fifth packet.<br>
**BadNet2:** This class introduces errors in every fifth packet.<br>
**BadNet3:** This class duplicates every fifth packet.<br>
**BadNet4:** This class reorders packets every fifth packet.<br>
**BadNet5:** This class combines errors, duplicates, drops, and reordering in every fifth packet.<br>

Each BadNet class has distinct behavior that you can use to test your program.

## Program Capabilities
The software effectively exhibits the following:

◆ Transferring files of different sizes, up to 2MB.<br>
◆ Successful transfer of files over a reliable network, without any errors, drops, or duplicates.<br>
◆ Handling different probabilities of network issues, such as dropped packets, duplicate packets, errors in packets, and out-of-order arrivals.<br>
◆ For dropped packets, they are retransmitted; duplicate packets are discarded; errors in packets are retransmitted; and out-of-order arrivals are re-ordered. It also handles any combination of these issues.<br>

## Selected Protocol
The protocol used in this task is **Go-Back-N** protocol which is a pipelined protocol and is also known as Automatic Repeat reQuest or Sliding Window Protocol. It is a data link layer protocol used in computer networks for reliable transmission of data packets. It is a type of sliding window protocol that allows the sender to transmit a number of packets before receiving an acknowledgment (ACK) signal from the receiver. The receiver can buffer a certain number of packets and send cumulative ACKs for them. If the sender does not receive an ACK within a certain time, it will retransmit all unacknowledged packets from the last acknowledged packet. This process continues until the sender receives an ACK for all packets sent or a certain number of retries is exceeded. 

## Functions Used
The following functions are used in the communication protocol:

◆ make_pkt(): generates an array that represents a packet with a particular sequence number, data, and checksum.<br>
◆ make_ack(): generates an array that represents an ACK signal at the receiving end with a specific sequence number and checksum.<br>
◆ notcorrupt(): compares the received checksum with the calculated checksum to check if the packet is corrupted or not.<br>
◆ hasseqnum(): utilized at the receiving end to verify if the received packet matches the expected packet with the same sequence number.<br>

## Group Members
◆ Hafsa Malik <br>
◆ Syeda Fatima Shahid 
