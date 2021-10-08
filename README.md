# ION - Network Connector
This repository contains recordings to demo the ION Network Connector

## Infor OS - ION Network Connectors: 

Connecting two different Infor OS environments to each other via ION Network Connector.

In the example we combine two different Multi Tenants of Infor OS, similar can be done for Single Tenant or On-Premises.

Connecting Multi Tenant to On-Premises or Multi Tenant to Single Tenant requires to open port 7443 and 443 for traffic from that Tenant.
  
Check https://docs.infor.com for documentation

For Infor Employees:
* Create Incident to open Single Tenant for traffic from that specific Multi-Tenant only. 
* Specify the relevant IP-addresses to be put on the Whitelist found at: https://wiki.infor.com/confluence/display/MTIOS/MT+Application+NAT+List
* If Single Tenant is not opened correctly for traffic from that MT the testing the Network Connector will result: Error occurred while generating Oauth access token for 'https://<customer>dev.cloud.infor.com:7443'. Reason: Unable to get Oauth20 token due to : Connection timed out

## Connecting Infor OS deployments, Multi Tenant & On Premises
* Bidirectional or Unidirectional (Receive from/ Send to Partner) integration
* Using ION API as proxy (authorized app)
* On Premises and Single Tenant using port 7443

![2021-10-08 10_21_48-Infor OS - ION Network Connectors v1 pptx - PowerPoint](https://user-images.githubusercontent.com/82956918/136523163-56ce72c5-fc3b-4f7e-a892-780550df1f7f.png)
## DEMO: using ION Network connection point (Unidirectional)
* Connecting Infor OS deployments, Two Multi Tenants
* First Unidirectional
* Send to Partner MingleTest1 & Receive from EDUGDENA031

![2021-10-08 10_15_45-Infor OS - ION Network Connectors v1 pptx - PowerPoint](https://user-images.githubusercontent.com/82956918/136522294-1f8e3692-4af6-40e9-aa52-5f7e911fe9c4.png)
### Summary
**On Receiving Tenant**
* Create Authorized App of type Backend Service,
* Download Credentials, Create Service Account,
* Download *.ionapi file
* Create Network Connection Point, import local *ionapi file
* Create Data Flow to process received documents
**On Sending Tenant**
* Create Network Connection Point, import remote *ionapi file
* Create Data Flow to generate documents to be sent
**BiDirectional**
* Same steps to be repeated vice versa

### ION API – Authorized App (Backend Service) 
**On Receiving Tenant**
* Create Authorized App of type Backend Service
* Download Credentials
* Create Service Account
* Download *.ionapi file

![image](https://user-images.githubusercontent.com/82956918/136524553-81be9385-2ea0-4658-bfb2-14547de5ac4a.png)
![image](https://user-images.githubusercontent.com/82956918/136524526-a418b24c-d442-4373-915c-12e60b1f3c2e.png)

### ION Desk - Network Connector (receiving)
**On Receiving Tenant:**
* Create Connection Point (ION Network)
* Direction: Receive from Partner
* Import Local *.ionapi
* Documents to be received from Partner (LN_Enum & LN_tcibd001)

![image](https://user-images.githubusercontent.com/82956918/136528718-241dd4e1-dcdf-4f69-a8a9-4d5fd8f75188.png)
![image](https://user-images.githubusercontent.com/82956918/136528744-6d29c0d0-a0d3-4355-9fce-5d32e8ba3872.png)
![image](https://user-images.githubusercontent.com/82956918/136528776-73d37cb6-8de2-4468-86a4-7c8defdbc5c0.png)
![image](https://user-images.githubusercontent.com/82956918/136528796-09699c4a-56dc-4b86-9194-bec158fdb46c.png)

### ION Desk - Data Lake Flow (receiving)
* Create Data Lake Flow (demo only)
* Select Documents (LN_Enum & LN_tcibd001)

![image](https://user-images.githubusercontent.com/82956918/136528941-353563fa-0539-4df8-8b0e-0f528c4f1140.png)
![image](https://user-images.githubusercontent.com/82956918/136528961-302649ca-9ca9-4b4d-a1ae-11d86bc8c33b.png)
![image](https://user-images.githubusercontent.com/82956918/136528974-9d11b821-ef27-4125-8ef5-85707a152ae9.png)

### ION Desk - Network Connector (sending)
**On Sending Tenant:**
* Create Connection Point (ION Network)
* Direction: Send to Partner
* Import Remote *.ionapi
* Documents to be sent to Partner (LN_Enum & LN_tcibd001)
* Testing connection is possible now  

![image](https://user-images.githubusercontent.com/82956918/136529055-cef925a1-4128-40e1-ba71-7b238be9601f.png)
![image](https://user-images.githubusercontent.com/82956918/136529080-e2280d5c-2ddf-4426-a715-1f270b0b54f8.png)
![image](https://user-images.githubusercontent.com/82956918/136529111-f80af346-2dc3-44db-b9f0-a6471c0ec047.png)

### ION Desk - Document Flow (sending)
* Create Document Flow
* Select Documents (LN_Enum & LN_tcibd001)

![image](https://user-images.githubusercontent.com/82956918/136529166-72ad2d58-825f-4106-b52c-3180773bf183.png)
![image](https://user-images.githubusercontent.com/82956918/136529176-47898a09-6f51-474e-9b0b-e4b893c5df35.png)
![image](https://user-images.githubusercontent.com/82956918/136529187-2d576fc3-edff-4f61-b50e-80d2fd706c19.png)

### ION Desk - OneView (testing)
* Trigger Documents in sending Application and check OneView
* Check OneView and receiving Application

![image](https://user-images.githubusercontent.com/82956918/136529219-ad4e7348-2ba8-45d7-9e58-35e98202d2e7.png)
![image](https://user-images.githubusercontent.com/82956918/136529237-ac9a1a0d-77c9-43e4-aa08-fea9fe9a5778.png)

## DEMO: using ION Network connection point (Bidirectional)
* Connecting Infor OS deployments, Two Multi Tenants
* BiDirectional =
  * Send to Partner MingleTest1 & Receive from EDUGDENA031
  * Send to EDUGDENA031 & Receive from Partner MingleTest1

![image](https://user-images.githubusercontent.com/82956918/136529302-c453b1e3-05cb-4227-ba7b-e72ebf662ebf.png)

### ION API - Authorized App (Backend Service)
**On Receiving Tenant:**
* Create Authorized App of type Backend Service
* Download Credentials
* Create Service Account
* Download *.ionapi file

![image](https://user-images.githubusercontent.com/82956918/136529506-847915f3-f241-4b55-9acb-648db79b5748.png)
![image](https://user-images.githubusercontent.com/82956918/136529519-83e7fbe3-0dc1-445e-bb1e-a709712e262a.png)

### ION Desk - Network Connector ( BiDirectional
**On the Receiving Tenant:**
* Change Connection Point (Network Connector)
* Direction: BiDirectional was “Send to Partner”
* Import Local *.ionapi
* Documents to be received from Partner (Process.ItemMaster)

![image](https://user-images.githubusercontent.com/82956918/136529688-982b3a5f-ffc5-4947-8984-e7572cafbe20.png)
![image](https://user-images.githubusercontent.com/82956918/136529709-8b453a15-4edd-49ed-898d-81501d43a777.png)

### ION Desk - Document Flow (receiving)
* Create Document Flow
* Select Documents (Process.ItemMaster)
  
![image](https://user-images.githubusercontent.com/82956918/136529748-be7fa864-06a1-4005-b29a-6d03261c7af6.png)
![image](https://user-images.githubusercontent.com/82956918/136529773-243c3d2e-b59b-493d-b654-1d6a5d963d05.png)

### ION Desk - Network Connector (sending)
**On the Sending Tenant:**
* Change Connection Point (Network Connector)
* Direction: BiDirectional was “Receive from Partner”
* Import Remote *.ionapi
* Select Documents (Process.ItemMaster Send To Partner)
* Testing connection is possible now

![image](https://user-images.githubusercontent.com/82956918/136529810-6e276443-b27c-4cb1-adb5-be6880fa59ea.png)
![image](https://user-images.githubusercontent.com/82956918/136529887-2d7b7d7f-ded0-4ac8-9b40-b54403d3ec6e.png)
![image](https://user-images.githubusercontent.com/82956918/136529942-5c084a58-a851-4ee2-abe7-8d9254931e8f.png)

### ION Desk - Document Flow (sending)
* Create Document Flow (IMS via ION API is used to publish documents to the Connection Point)
* Select Documents (Process.ItemMaster)

![image](https://user-images.githubusercontent.com/82956918/136530196-83ac040b-ffdd-4fba-84c6-8b375063b5d5.png)
![image](https://user-images.githubusercontent.com/82956918/136530212-5be40f02-16d3-4cc6-b8b5-0d15d7564add.png)

### ION Desk - OneView (testing)
* Trigger Documents in sending Application
* Check OneView and receiving Application
  
![image](https://user-images.githubusercontent.com/82956918/136530464-3e978f6e-6ce4-477f-b952-9aa71743e45e.png)
![image](https://user-images.githubusercontent.com/82956918/136530483-3ca9ee13-c7d1-4315-b4e5-7349c071d593.png)
