# Overview 

The goal of this assignment is to further practice computing network performance metrics based on given scenarios.

# Instructions

Answer the following questions by showing your work. You should write your responses directly in this Markdown file.

# Q1

Suppose Host A wants to send a 7 MB file to Host B. The path between Host A and Host B includes three links with the following capacities and current usage levels:

* Link 1: 1 Mbps (30% utilized)
* Link 2: 800 Kbps (10% utilized)
* Link 3: 3 Mbps (70% utilized)

Questions:

* What is the effective throughput available for the file transfer?
* Approximately how long will it take for the file to reach Host B?

```
available bandwith
  link 1: 1 Mbps * 0.7 = 700 Kbps
  link 2: 800 Kbps * 0.9 = 720 Kbps
  link 3: 3 Mbps * 0.3 = 900 Kbps

since throughput is the slowest link, effective throughput is 700 Kb.
  7 MB is 56000 Kb
  56,000 Kb / 700 kbps = 80s
```

# Q2

How many bits are expected to arrive with errors during the transmission of a 500 MB file, assuming a bit error rate (BER) of 10^-6?

```
10^-6 is 1/1,000,000 rate of error per millions of bits.
  500 MB is 4,000,000,000 bits
  4B/1M = 4K or 4,000 bit errors for a 500 MB file.
```

# Q3

![pic1.png](pics/pic1.png)

What is the overhead percentage of an Ethernet frame that carries 500 bytes of payload?

Refer to the Ethernet frame structure shown above. Show your work and explain your reasoning.

```
6 + 6 + 2 + DATA size + 4. Now, we 18 / DATA size + 18 to determine overhead percentage
  DATA size = 500 bytes -> 18/518 = 0.0347 * 100 = 3.47%
```

# Q4

A packet sent to a target host must travel through three hops, with each intermediate device introducing the following delays:

* Hop 1: 3 ms
* Hop 2: 5 ms
* Hop 3: 2 ms

What is the total end-to-end delay for the transmission?

```
packet to hop 1 = +3 ms
packet to hop 2 = +5 ms
packet to hop 3 = +2 ms
  total end-to-end time is +10 ms.
```

# Q5

A router has an input queue that can hold up to 10 packets. Each packet takes 0.5 ms to be processed. If the router already has 7 packets in its input queue, what is the expected queuing delay for a newly arriving packet?

```
slot10:
slot 9:
slot 8: our packet
slot 7: some packet +3.5 ms
slot 6: some packet +3.0 ms
slot 5: some packet +2.5 ms
slot 4: some packet +2.0 ms
slot 3: some packet +1.5 ms
slot 2: some packet +1.0 ms
oldest -> slot 1: some packet +0.5 ms
  it'll take our packet 3.5 ms before it starts processing and 4.0 ms to end processing.
```

# Submission

Update your remote repository by pushing this README file. 
