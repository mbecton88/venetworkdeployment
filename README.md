# Project 1: Secure Virtual Network and VM Deployment

For my first project, I wanted to showcase my ability to build a secure and functional network environment in Azure. I started by planning out my virtual network, deciding I needed a public subnet for internet-facing resources and a private subnet for backend systems.

## Technologies Used:

* **Microsoft Azure:**
    * Virtual Networks (VNets)
    * Subnets
    * Virtual Machines (VMs) (Windows Server 2019, Ubuntu Linux)
    * Network Security Groups (NSGs)
    * Public IP Addresses
    * Resource Groups
* **Protocols:**
    * RDP (Remote Desktop Protocol)
    * SSH (Secure Shell)
    * HTTP
    * HTTPS
## Virtual Network Creation:

First, I went into the Azure portal and created a new resource group for the project and named it SecureNetworkRG. Then I created a virtual network. I named it 'SecureVNet' and chose a suitable address space. I then created two subnets: 'PublicSubnet' and 'PrivateSubnet,' each with its own address range.<br>

![image](https://github.com/user-attachments/assets/e8733e52-0622-4a76-8053-dabd0ef0cf34)<br>
![image](https://github.com/user-attachments/assets/331abde6-f780-4137-9a71-c8f98511b158)<br>


## Virtual Machine Deployment:

Next, I deployed a Windows Server 2019 VM into the 'PublicSubnet.' I named it 'WebVM' and chose a small, cost-effective VM size. I also deployed a Linux Ubuntu VM into the 'PrivateSubnet,' naming it 'DatabaseVM.' I used SSH keys for secure access to the Linux VM.<br>

![image](https://github.com/user-attachments/assets/599eed19-0fb6-449e-bff0-872cbf3770f3)<br>
![image](https://github.com/user-attachments/assets/a82208ee-0164-4f70-a1ed-35e23ddf71c5)<br>
![image](https://github.com/user-attachments/assets/223809fc-b3b7-4384-a4fa-92a08cff37b3)<br>
![image](https://github.com/user-attachments/assets/cc4ba5b1-cf1d-49ea-8244-f81eee62ba2b)<br>

## Network Security Groups (NSGs):

Security was a top priority. I created two NSGs: 'PublicNSG' and 'PrivateNSG.' For 'PublicNSG,' I configured inbound rules to allow RDP access only from my specific IP address, and I allowed HTTP and HTTPS traffic. For 'PrivateNSG,' I allowed SSH access from my IP address. I also created a rule to allow the 'WebVM' to connect to the 'DatabaseVM' on the database port.

## Public IP Address:

To enable remote access to the 'WebVM,' I created a public IP address and associated it with the VM's network interface.

## Testing and Verification:

Finally, I tested the setup. I was able to RDP into the 'WebVM' from my computer. I also verified that the 'WebVM' could connect to the 'DatabaseVM' on the specified port. I then deleted the resource group to prevent any further charges.

