# Active Directory Simulation using Vmware
![Copy of Log ana](https://github.com/emeka789/ActiveDirectoryHL/assets/99328320/dd1d99dc-b7b0-44c5-88e1-c6b6a661fe03)
## Summary
In this project, Vmware was used to simulate a corporate environment consisting of a client machine (Win 10), domain controller hosting Active Directory (Win Server 2019), as well as other network services needed to segment the network (NAT/RAS, DNS, DHCP). A custom Powershell script was used to create 1000 fictional users each given a username and password for clients to access the environment. Active directory was then leveraged to create organizational units (OU), group policies (GP), and security groups (SG) to structure, centralize, and manage user accounts, computers, and other network resources within the simulated corporate environment.

## Tools and Technologies Used
- Vmware
- Windows Server 2019
- Client Machine (Windows 10)
- Active Directory
- Active Directory Domain Services
- Domain Naming System (DNS)
- Dynamic Host Configuration Protocol (DHCP)
- Network Address Translation (NAT)
- Powershell
- File and Storage Services

## Windows Server 2019 and Active Directory Configuration
Two network adapters were used to separate internal and external traffic.
![Screenshot 2023-06-20 031608](https://github.com/emeka789/ActiveDirectoryHL/assets/99328320/d56b7c86-48e2-42ec-9d84-7e447dacfb09)

The following roles and services for Active Directory and the Domain Controller were configured
![286363729-25d70bde-a64a-4de3-bf8d-4ade4bd69542](https://github.com/emeka789/ActiveDirectoryHL/assets/99328320/2b2684f2-b08e-4e7b-a9ca-bc6db37f2534)

Powershell scripts were then used to create 1000 fictional users as well as user creation within the Active Directory environment.
![Screenshot 2023-06-10 122014](https://github.com/emeka789/ActiveDirectoryHL/assets/99328320/20edc126-173a-42b0-ac63-6ba445a0f5ec)

![Screenshot 2023-06-20 031927](https://github.com/emeka789/images/assets/99328320/f7def568-94e3-4f49-aa13-a88ded8341f4)
![Screenshot 2023-06-20 031830](https://github.com/emeka789/images/assets/99328320/9f5d211d-1aee-4c4d-aba2-d4b78201c956)

### Step 5: Additional Considerations (optional)
- Configure Group Policies to enforce security settings and apply specific configurations.
- Set up file sharing and folder redirection for centralized file storage and access.
- Integrate additional services such as DNS, DHCP, or Certificate Authority to enhance the home lab setup.

## Conclusion
Congratulations! You have successfully set up a home lab with a domain controller and client machine. This environment will enable you to learn, test, and experiment with various networking and security configurations. Feel free to explore further possibilities and expand your home lab setup.

