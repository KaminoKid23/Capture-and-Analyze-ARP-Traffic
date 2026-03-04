# ARP Traffic Capture and Analysis

## Project Overview

This project demonstrates the capture and analysis of Address Resolution Protocol (ARP) traffic within a local network environment using Wireshark. The lab explores how devices resolve IP addresses to MAC addresses, how ARP packets are structured, and how abnormal broadcast behavior can be identified through traffic monitoring.

The goal of this project was to observe ARP communication in real time, analyze packet-level details, and understand how excessive ARP traffic impacts network behavior.

---

## Objectives

* Identify local network configuration, including the default gateway
* Clear and inspect ARP cache entries
* Capture ARP traffic using Wireshark
* Analyze ARP request packet structure
* Interpret Ethernet frame fields and EtherType values
* Monitor and analyze abnormal ARP broadcast activity

---

## Project Process

### 1. Network Configuration Discovery

The system’s IP configuration was reviewed to identify the default gateway. This gateway address was used to generate ARP traffic for analysis.

### 2. ARP Cache Clearing and Traffic Generation

The ARP cache was cleared to remove existing IP-to-MAC mappings. A connection attempt to the default gateway forced the system to send a new ARP request, allowing the resolution process to be captured in Wireshark.

### 3. Packet Capture and Inspection

Using Wireshark, ARP packets were filtered and examined in detail. The analysis included:

* Ethernet broadcast destination address (`ff:ff:ff:ff:ff:ff`)
* EtherType `0x0806`, identifying ARP protocol traffic
* Sender MAC and IP address fields
* Target MAC address behavior during an ARP request (all zeros)
* The role of the ARP reply in completing MAC address resolution

This portion of the project reinforces understanding of how local network devices dynamically resolve Layer 3 addresses to Layer 2 hardware addresses.

### 4. ARP Storm Observation

Wireshark was configured to monitor ARP traffic levels. During a simulated ARP storm scenario, traffic graphs displayed a significant increase in broadcast packets. Alerts and packet analysis tools were used to observe abnormal network behavior and identify malformed packet activity.

---

## Key Concepts Demonstrated

* ARP request and reply communication
* IP-to-MAC address resolution
* Ethernet frame structure
* Broadcast vs. unicast traffic
* ARP cache functionality
* Traffic spike identification using graphical analysis
* Basic detection of abnormal Layer 2 behavior

---

## Repository Structure

```id="proj1"
ARP-Traffic-Analysis/
│
├── README.md
└── screenshots/
    ├── 01_Discover_Default_Gateway_IPConfig.png
    ├── 02_Clear_ARP_Cache_and_Ping_Default_Gateway.png
    ├── 03_View_ARP_Table_Entries.png
    ├── 04_Wireshark_Captured_ARP_Traffic.png
    ├── 05_ARP_Packet_Ethernet_Broadcast_Details.png
    ├── 06_Wireshark_ARP_Storm_Detection_Configuration.png
    ├── 07_ARP_Storm_Traffic_Graph_Initial.png
    ├── 08_ARP_Storm_Traffic_Graph_Midpoint.png
    ├── 09_ARP_Storm_Traffic_Graph_10_Minute_Analysis.png
    ├── 10_Wireshark_Abnormal_Traffic_Alert.png
    ├── 11_Wireshark_Malformed_Packet_Report.png
    └── 12_ARP_Request_Packet_Analysis.png
```

---

## Summary

This project provides a practical examination of ARP traffic within a local network. By capturing and analyzing packet-level data, it illustrates how address resolution functions and how abnormal broadcast behavior can be detected through network monitoring tools.
