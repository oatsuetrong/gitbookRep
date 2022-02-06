---
description: >-
  Cisco® Software-Defined Access (SD-Access) is a solution within Cisco Digital
  Network Architecture (Cisco DNA), which is built on intent-based networking
  principles.
---

# SD-Access Solutions

## [Benefits](https://www.cisco.com/c/en/us/solutions/collateral/enterprise-networks/software-defined-access/solution-overview-c22-739012.html#Benefits)

As one of the three pillars of Cisco zero-trust security framework, SD-Access combines security and networking operations. It assists security by enhancing visibility, defining access policies, and improving trust. It improves networking operations by automating network configurations to implement these policies.

* **Identify, profile, and group endpoints:** SD-Access uses AI- and ML-based advanced analytics for endpoint identification and grouping. It analyzes traffic flows between groups and define effective access policies.
* **Segment network based on defined policies:** SD-Access applies group-based access policies for effective multilevel segmentation, leading to zero-trust security.
* **Analyze endpoint behavior and verify trust:** SD-Access continuously scrutinizes endpoint behavior, scans for vulnerabilities, and verifies their trustworthiness for continued access.
* **Rapidly contain threats and prevent data breaches:** SD-Access reduces zones of trust, isolates rogue or compromised endpoints, and enhances regulatory compliance.

![SD-Access overview](../../.gitbook/assets/solution-overview-c22-739012\_0.webp)

## [SD-Access constituent products](https://www.cisco.com/c/en/us/solutions/collateral/enterprise-networks/software-defined-access/nb-06-simple-steps-to-sd-access-wp-cte-en.html#SDAccessconstituentproducts)

Cisco DNA Center, Cisco Identity Services Engine (ISE), and the entire networking infrastructure form the set of products necessary for SD-Access.

**Cisco DNA Center:** As a network management system and controller, Cisco DNA Center provides a dashboard for user interaction, an automation engine to configure devices, an AI/ML analytics engine to ingest network data and derive useful insights, and a variety of integrations with security applications. As part of the automation, Cisco DNA Center allows network engineers to set up configuration templates that it customizes and pushes into network devices. Cisco DNA Center also hosts applications such as Cisco AI Endpoint Analytics, Cisco Group-Based Policy Analytics, Access Control Application, and others that SD-Access uses.

![Cisco DNA Center 1.3.3.5 Dashboard](../../.gitbook/assets/cisco-sda-design-guide\_1.webp)

**Cisco ISE:** As an authentication and authorization server, Cisco ISE acts as the policy repository and enforcement engine and works with Cisco DNA Center as part of the SD-Access solution. It obtains policy definitions from the Cisco DNA Center, identifies and groups endpoints as they first access the network, and dynamically programs the relevant access privileges to the switch port for the endpoint.

**Network infrastructure:** SD-Access works with all Cisco Catalyst® switches, routers, wireless access points, and LAN controllers introduced in the past decade. While the entire set of SD-Access features is fully supported by the Catalyst 9000 family of devices, the level of support may be lower in previous generation devices. \


## [SD-Access Fabric Roles and Terminology](https://www.cisco.com/c/en/us/td/docs/solutions/CVD/Campus/cisco-sda-design-guide.html#SDAccessFabricRolesandTerminology)

A fabric role is an SD-Access software construct running on physical hardware. These software constructs were designed with modularity and flexibility in mind.

![SD-Access Fabric Roles – Example](https://www.cisco.com/c/dam/en/us/td/docs/solutions/CVD/Campus/cisco-sda-design-guide.docx/\_jcr\_content/renditions/cisco-sda-design-guide\_8.jpg)

### Control Plane Node

The SD-Access fabric control plane node is based on the LISP Map-Server and Map-Resolver functionality combined on the same node. The control plane node’s database tracks all endpoints in the fabric site and associates the endpoints to fabric nodes, decoupling the endpoint IP address or MAC address from the location (closest router) in the network.

### Edge Node

The SD-Access fabric edge nodes are the equivalent of an access layer switch in a traditional campus LAN design. The edge node functionality is based on the Ingress and Egress Tunnel Routers (xTR) in LISP. The edge nodes must be implemented using a Layer 3 routed access design.

### Intermediate Node

Intermediate nodes are part of the Layer 3 network used for interconnections among the devices operating in a fabric role such as the interconnections between border nodes and edge nodes.  These interconnections are created in the Global Routing Table on the devices and is also known as the [_underlay network_](https://www.cisco.com/c/en/us/td/docs/solutions/CVD/Campus/cisco-sda-design-guide.html#Underlay).

### Border Node

The fabric border nodes serve as the gateway between the SD-Access fabric site and the networks external to the fabric. The border node is responsible for network virtualization interworking and SGT propagation from the fabric to the rest of the network.

### Fabric WLC

Both fabric WLCs and non-fabric WLCs provide AP image and configuration management, client session management, and mobility services.  Fabric WLCs provide additional services for fabric integration such as registering MAC addresses of wireless clients into the [host tracking database](https://www.cisco.com/c/en/us/td/docs/solutions/CVD/Campus/cisco-sda-design-guide.html#HTDB) of the fabric control plane nodes during wireless client join events and supplying fabric edge node RLOC-association updates to the HTDB during client roam events.
