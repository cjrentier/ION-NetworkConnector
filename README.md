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
