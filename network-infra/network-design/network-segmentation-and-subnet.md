---
description: >-
  Reference:
  https://www.cisco.com/c/dam/en/us/td/docs/solutions/CVD/Campus/CVD-Software-Defined-Access-Segmentation-Design-Guide-2018MAY.pdf
---

# Network Segmentation and Subnet

## Network segmentation overview

The concept of network segmentation is not new, but it has evolved significantly over the last 20 or so years. Initially, network segmentation was defined as the process of breaking up one “flat” network/broadcast domain into smaller segments through the use of virtual LANs (VLANs). The original intent was to improve the overall performance of not only the network itself but also the endpoints by minimizing the number of broadcasts devices had to process.

However, as time went on, network segmentation through the use of VLANs was implemented for security reasons and for the ability to limit communications between segments through the use of Access Control Lists (ACLs) to enforce a business-related policy. VLANs initially provided a very basic means of isolating one segment (VLAN) and its devices from another. Private VLANs later provided a form of micro-segmentation, by further restricting communications within a VLAN.

Over the last 10 years Cisco developed a new technology known as Cisco TrustSec® that ultimately redefined the term “network segmentation.” With Cisco TrustSec, segmentation is no longer performed based on VLANs or VRFs with IP addressing and routing. Instead, Cisco TrustSec relies on the use of role- or group-based membership, irrespective of IP addressing, to create policies allowing for segmentation of the network.

### Cisco TrustSec

The Cisco TrustSec solution establishes clouds of trusted network devices to build secure networks. The TrustSec solution uses the device and user identity information that it obtains during authentication to classify. The tag, also called the security group tag (SGT), allows [Cisco ISE ](sda.md#sd-access-constituent-products)to enforce access control policies by enabling the endpoint device to act upon the SGT to filter traffic. In briefly, user that in different SGT.

ISE provides a matrix view of our SGT's where can decided who can talk to who, the image below shows an example of this.

![](https://blog.jack.cloud/content/images/2016/11/trustsec-ise-matrix.png)

![Example of SGTs Matrix in ISE](https://www.cisco.com/c/dam/en/us/support/docs/security/identity-services-engine-24/213616-how-to-configure-cisco-trustsec-sgts-u-18.png)

### Security Group

| Name                | Description                                               |   |
| ------------------- | --------------------------------------------------------- | - |
| Employee\_HR        | SGT for employee who in Human Resource department         |   |
| Employee\_Marketing | SGT for employee who in Marketing department              |   |
| Employee\_Financial | SGT for employee who in Financial department              |   |
| Employee\_IT        | SGT for employee who in Information Technology department |   |
| Employee\_Executive | SGT for employee who in Administrative department         |   |
| Employee\_BYOD      | SGT for employee who use BYOD                             |   |

### Subnet

| Endpoint Type    | IP Network     | IP Range Usage           | Usable Hosts |
| ---------------- | -------------- | ------------------------ | ------------ |
| PC/Laptop        | 10.1.20.0/24   | 10.1.20.1-10.1.20.254    | 254          |
| IP Phone         | 10.1.21.0/24   | 10.1.21.1-10.1.21.254    | 254          |
| Printer          | 10.1.10.0/26   | 10.10.10.1-10.1.10.62    | 62           |
| Access Point     | 10.1.10.64/26  | 10.1.10.65-10.1.10.126   | 62           |
| CCTV             | 10.1.10.128/26 | 10.10.10.129-10.1.10.190 | 62           |
| Face Recognition | 10.1.10.192/26 | 10.1.10.193-10.1.10.254  | 62           |
