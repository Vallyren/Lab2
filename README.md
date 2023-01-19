# Lab2
## Lab - Configure Automated Security Features
### Topology
##### ![Topology](https://user-images.githubusercontent.com/122459067/213380189-26b6bfbf-6f84-4dbe-bec8-9c06ad7a2c1e.png)
###	Addressing Table
##### ![Adressing table](https://user-images.githubusercontent.com/122459067/213380568-19a8a1b5-31b7-4ca4-8929-a34b2a81f4a7.png)
### Objectives
#### Part 1: Configure Basic Device Settings
##### Cable the network as shown in the topology.
# ![Scheme](https://user-images.githubusercontent.com/122459067/213385828-e3e64fe2-75a4-4941-9484-35d824b23ad5.png)
##### Configure basic IP addressing for routers and PCs.
##### R1
###### ![R1-1](https://user-images.githubusercontent.com/122459067/213383433-12186c1f-63c8-4502-807f-f09996fa053e.png)
##### R2
###### ![R2-1](https://user-images.githubusercontent.com/122459067/213384290-224ac396-22c0-4e6d-8bb9-86683a640ab1.png)
##### R3
###### ![R3-1](https://user-images.githubusercontent.com/122459067/213385140-a069b826-1924-4219-b99b-c822d349f055.png)
##### Configure OSPF routing.
##### R1
###### ![R1-2](https://user-images.githubusercontent.com/122459067/213414059-d1825eec-f09b-41c5-92f0-ef98c3264c68.png)
##### R2
###### ![R2-2](https://user-images.githubusercontent.com/122459067/213414538-61c39255-aad4-4bc3-9751-d4c93c16769d.png)
##### R3
###### ![R3-2](https://user-images.githubusercontent.com/122459067/213414924-1f56fdda-fde0-40d3-bc04-11683506cba7.png)
##### Configure PC hosts.
##### PC-A
###### ![PC-A](https://user-images.githubusercontent.com/122459067/213416099-0a481f46-acfb-4b1b-ab4c-bc739aaf6b6c.png)
##### PC-C
###### ![PC-C](https://user-images.githubusercontent.com/122459067/213416604-6d4fa9ec-f5f5-48b6-ad08-84d0618c91ac.png)
##### Verify connectivity between hosts and routers.
###### a.	Ping from R1 to R3.
![ping r1 r3](https://user-images.githubusercontent.com/122459067/213417359-474522b8-dac4-4187-a75d-476678e0ad14.png)
###### b.	Ping from PC-A, on the R1 LAN, to PC-C, on the R3 LAN.
![pca tto pcc](https://user-images.githubusercontent.com/122459067/213418796-35877550-a212-443f-8cd4-5122c74d3769.png)
#### Part 2: Configure Automated Security Features
##### Lock down a router using AutoSecure and verify the configuration.
![2023-01-19_14-28-46](https://user-images.githubusercontent.com/122459067/213434080-320554de-7692-4d15-8eeb-7b0c35d50f6b.png)
![2023-01-19_14-29-22](https://user-images.githubusercontent.com/122459067/213434077-08f36418-741d-47f2-b074-79349cb6e842.png)
![2023-01-19_14-34-39](https://user-images.githubusercontent.com/122459067/213434074-fba20314-0f26-4db1-b129-2f4c328912b4.png)
![2023-01-19_14-42-12](https://user-images.githubusercontent.com/122459067/213434067-5e1147ea-9313-447b-9d5e-7e51627c390e.png)
##### Contrast using AutoSecure with manually securing a router using the command line.
###### Establish an SSH connection from PC-C to R3.
![2023-01-19_15-27-03](https://user-images.githubusercontent.com/122459067/213443065-e74a641e-b40a-4ff5-a3a6-29a3a2b8e98c.png)
![2023-01-19_15-27-23](https://user-images.githubusercontent.com/122459067/213443063-c1bdfde9-9959-4e1f-9f8a-0cb91c3de479.png)
![2023-01-19_15-27-40](https://user-images.githubusercontent.com/122459067/213443057-a2489e70-4c22-4442-8a8e-11711e22b18f.png)
##### Contrast the AutoSecure-generated configuration of R3 with the manual configuration of R1.
###### What security-related configuration changes were performed on R3 by AutoSecure that were not performed in previous sections of the lab on R1?
AutoSecure: AAA, tcp interception function, logging trap debugging, logging buffering, logging console criticality enabled. Ip http server, cdp and other secondary services are disabled. Console, AUX, and vty inputs are configured for local authentication. A permissive password has been created. The minimum length of security passwords has been changed to 6.
###### What security-related configuration changes were performed in previous sections of the lab that were not performed by AutoSecure?
Telnet access was excluded from vty transport input. Additional accounts were created.
###### Identify at least five unneeded services that were locked down by AutoSecure and at least three security measures applied to each interface.
Services disabled include:
no service finger
no service pad
no service udp-small-servers
no service tcp-small-servers
no cdp run
no ip bootp server
no ip http server
no ip finger
no ip source-route
no ip gratuitous-arps
no ip identd
For each interface, the following were disabled:
no ip redirects
no ip proxy-arp
no ip unreachables
no ip directed-broadcast
no ip mask-reply
###### What are some advantages to using AutoSecure?
It can detect security vulnerabilities and lock down the router much faster, eliminating the need to use Cisco IOS commands and procedures.

