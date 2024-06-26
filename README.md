# ABSTRACT

This project outlines the deployment of a secure web application behind a firewall on Azure. The key objectives include setting up a virtual network, deploying an Ubuntu virtual machine, configuring Azure Firewall with DNAT rules, and using Azure Bastion for secure access. The project ensures that the web application is accessible only to specific IP addresses, enhancing security.

# INTRODUCTION

In today's digital landscape, securing web applications is crucial to prevent unauthorized access and data breaches. Azure provides various services that enable the deployment of secure applications in the cloud. This project explores the deployment of a web application on an Ubuntu VM within an Azure virtual network, secured by Azure Firewall and accessible via Azure Bastion. The configuration ensures that only specific IP addresses can access the application, thereby enhancing its security.

This document is structured to provide a comprehensive guide on deploying a secure web application behind a firewall on Azure. It begins with an Abstract, offering a high-level overview of the project's objectives and outcomes. The Introduction section elaborates on the importance of securing web applications and introduces the core Azure services used. In the Method and Materials/Resources Used section, detailed steps are provided for setting up the Azure environment, deploying a virtual machine, and configuring Azure Firewall and Bastion, including specific commands and configurations. The Results section presents the outcomes of the deployment, highlighting the successful access control achieved through the firewall settings. Finally, the Conclusion summarizes the project, emphasizing the enhanced security and applicability of the setup for sensitive web applications.

RESOURCES AND PURPOSE

1. Azure Portal & Valid Subscription
Purpose - To create and manage Azure resources.

2. Resource Group 
Purpose - To group all related resources for easier management and organization.
Resource - “Resource Group”

![Screenshot (80)](https://github.com/sohamk1112/Secure-Deployment-of-a-Web-Application-Behind-an-Azure-Firewall/assets/85565566/5ce710a3-e3db-4857-bc06-168aa0a2fb63)


3. Virtual Network
Purpose - To create a private network for the virtual machine.
Resource - “Virtual Network”

![Screenshot (81)](https://github.com/sohamk1112/Secure-Deployment-of-a-Web-Application-Behind-an-Azure-Firewall/assets/85565566/9d13a5ec-8156-4e92-99ca-a6631b89bfd8)

4. Virtual Machine
Purpose - To host the web application.
Resource - “Virtual Machine”

![Screenshot (82)](https://github.com/sohamk1112/Secure-Deployment-of-a-Web-Application-Behind-an-Azure-Firewall/assets/85565566/b2499142-3932-4a81-a981-78c957974695)


6. Azure Bastion
Purpose - To provide secure and seamless RDP and SSH connectivity to virtual machines without exposing them to the public internet.
Resource - “Azure Bastion”

![Screenshot (83)](https://github.com/sohamk1112/Secure-Deployment-of-a-Web-Application-Behind-an-Azure-Firewall/assets/85565566/99d3741c-b517-4929-82a9-a8be44285b74)


7. Public IP Address
Purpose - To enable Azure Bastion for secure SSH access.
Resource - “Public IP Address for Azure Bastion”



8. Azure Firewall
Purpose - To control and filter network traffic to and from the virtual network.
Resource - “Azure Firewall”
Tier - Standard

![Screenshot (84)](https://github.com/sohamk1112/Secure-Deployment-of-a-Web-Application-Behind-an-Azure-Firewall/assets/85565566/a3742228-3a4c-43f2-a724-becc51681ef0)



10. Firewall Policy
Purpose: To define access rules for the Azure Firewall.
Resource: “Firewall Policy”

![Screenshot (85)](https://github.com/sohamk1112/Secure-Deployment-of-a-Web-Application-Behind-an-Azure-Firewall/assets/85565566/e8025e6f-bb74-48b8-8a54-9850a88e4524)


11. OS: Ubuntu Server 20.04 LTS X64 Gen2
Administrator Account - SSH public key
Username - “azureuser”

12. SSH Key Pair
Purpose - For secure SSH access to the virtual machine.
Resource - “SSH Key Pair”

13. Nginx Web Server
Purpose - To serve the static website.
Resource - “Nginx”

![Screenshot (88)](https://github.com/sohamk1112/Secure-Deployment-of-a-Web-Application-Behind-an-Azure-Firewall/assets/85565566/27d19fd0-780c-4744-a999-12fdf0e04962)
![Screenshot (89)](https://github.com/sohamk1112/Secure-Deployment-of-a-Web-Application-Behind-an-Azure-Firewall/assets/85565566/bce905b7-28e0-49b3-9fad-ea9bb5c5765e)




15. Firewall DNAT Rules
Purpose - To configure network address translation and control inbound traffic to the virtual machine.
Resource - “DNAT Rules” 

16. Rule Collection 
Name - “firewall-nginx-rule”
Priority - 100
Source Type - IP address (specific to the user’s PC)
Destination IP Address - Firewall’s public IP address
Protocol - TCP
Destination Port - 9000
Translated Address - Private IP address of the virtual machine
Translated Port – 80
![Screenshot (87)](https://github.com/sohamk1112/Secure-Deployment-of-a-Web-Application-Behind-an-Azure-Firewall/assets/85565566/0e40f3bc-da5b-45d4-b288-cd8510e02a5b)



# RESULTS

The deployment was successful, with the web application accessible only from the specified IP addresses. The HTML content served by Nginx was displayed correctly when accessed from allowed IP addresses, demonstrating the effectiveness of the configured DNAT rules. Unauthorized access attempts from other IP addresses were blocked by Azure Firewall.

![Screenshot (86)](https://github.com/sohamk1112/Secure-Deployment-of-a-Web-Application-Behind-an-Azure-Firewall/assets/85565566/3ab4076c-061e-47aa-a55b-4635925ec6e5)




# CONCLUSION

This project successfully demonstrates the deployment of a secure web application on Azure using Azure Bastion for secure VM access and Azure Firewall to control inbound traffic. The configuration ensures that the application is only accessible to specific IP addresses, significantly enhancing security. This setup is ideal for scenarios requiring strict access control to sensitive web applications, showcasing the robustness and flexibility of Azure's networking and security features

# KEYWORDS

Azure DevOps, Cloud Computing, Azure Firewall, Azure Bastion, Virtual Machine (VM), Virtual Network (VNet), Secure Web Application, Nginx, Ubuntu Server, Dynamic Network Address Translation (DNAT), Public IP Address, Private IP Address, Firewall Policy, SSH Authentication, Resource Group, Azure Networking, Web Server Deployment, Network Security, Access Control, Secure Remote Access, IP Address Whitelisting, Infrastructure as a Service (IaaS), Azure Portal, Cloud Security, Package Management, System Updates, Firewall Rule Configuration, Network Interface Card (NIC), TCP Protocol, Static Website Hosting, Linux Command Line, Command Line Interface (CLI), Systemctl, Sudo Commands, Azure Resource Management, Network Security Group (NSG), Internet Protocol (IP), Azure Subscription, Cloud Infrastructure, DevOps Practices
