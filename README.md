# ION - Network Connector
This repository contains recordings to demo the ION Network Connector

- Infor OS - ION Network Connectors V1: 
  
  Connecting two different Infor OS environments to each other via ION Network Connector.
  In the example we combine two different Multi Tenants of Infor OS, similar can be done for Single Tenant or On-Premises.
  Connecting Multi Tenant to On-Premises or Multi Tenant to Single Tenant requires to open port 7443 and 443 for traffic from that Tenant.
  
  Check https://docs.infor.com for documentation
  
  For Infor Employees:
    
    Create Incident to open Single Tenant for traffic from that specific Multi-Tenant only. 
    
    Specify the relevant IP-addresses to be put on the Whitelist found at: https://wiki.infor.com/confluence/display/MTIOS/MT+Application+NAT+List 
    
    If Single Tenant is not opened correctly for traffic from that MT the testing the Network Connector will result: Error occurred while generating Oauth access token for 'https://<customer>dev.cloud.infor.com:7443'. Reason: Unable to get Oauth20 token due to : Connection timed out

## Connecting Infor OS deployments, Multi Tenant & On Premises
* Bidirectional or Unidirectional (Receive from/ Send to Partner) integration
* Using ION API as proxy (authorized app)
* On Premises and Single Tenant using port 7443

![2021-10-08 10_21_48-Infor OS - ION Network Connectors v1 pptx - PowerPoint](https://user-images.githubusercontent.com/82956918/136523163-56ce72c5-fc3b-4f7e-a892-780550df1f7f.png)
## ION Network connection point (demo)
* Connecting Infor OS deployments, Two Multi Tenants
* First Unidirectional
* Send to Partner MingleTest1 & Receive from EDUGDENA031

![2021-10-08 10_15_45-Infor OS - ION Network Connectors v1 pptx - PowerPoint](https://user-images.githubusercontent.com/82956918/136522294-1f8e3692-4af6-40e9-aa52-5f7e911fe9c4.png)
### Summary
* **On Receiving Tenant**
  * Create Authorized App of type Backend Service,
  * Download Credentials, Create Service Account,
  * Download *.ionapi file
  * Create Network Connection Point, import local *ionapi file
  * Create Data Flow to process received documents
* **On Sending Tenant**
  * Create Network Connection Point, import remote *ionapi file
  * Create Data Flow to generate documents to be sent
* **BiDirectional**
  * Same steps to be repeated vice versa
  
