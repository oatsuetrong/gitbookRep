# Wireless Design

## Campus Floorplan Heatmap

### Floor 1 - Headquarter Campus

### Floor 2 - Headquarter Campus

### Floor 3 - Headquarter Campus

### Floor 4 - Headquarter Campus

### Floor 1 - Branch Campus

## WLAN SSID

| SSID              | Band          | Authentication Method           | Description                                                    |
| ----------------- | ------------- | ------------------------------- | -------------------------------------------------------------- |
| LoanShark-HQ      | 2.4 GHz/5 GHz | 802.1x (Username and Password)  | For employee in the organization.                              |
| LoanShark-Exec    | 2.4 GHz/5 GHz | Add manually MAC address in ISE | For employee who in Administrative department of organization. |
| .@ AIS SUPER WiFi | 2.4 GHz/5 GHz | Web portal login                | Public Wi-Fi for customer who came in the bank. Using          |
| AIS SMART Login   | 2.4 GHz/5 GHz | Web portal login                | Public Wi-Fi for customer who came in the bank.                |

#### [What is IEEE 802.1X](https://www.securew2.com/solutions/802-1x#:\~:text=802.1X%20is%20a%20network,confirmed%20by%20the%20RADIUS%20server.)

802.1x - it has an authentication server called a RADIUS Server. It checks a user's credentials to see if they are an active member of the organization and, depending on the network policies, grants users varying levels of access to the network. This allows unique credentials or certificates to be used per user, eliminating the reliance on a single network password that can be easily stolen. User in organization can login via Cisco AnyConnect software on a PC/Laptop by using their employee number and password to access the organization network.

![802.1x Workflow](https://www.securew2.com/wp-content/uploads/2021/12/what-is-ieee.svg)

AIS SUPER WiFi / Web portal

Customer can user the AIS mobile number to login .......&#x20;
