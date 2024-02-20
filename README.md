# Active Directory Simulation using Vmware
![Copy of Log ana](https://github.com/emeka789/ActiveDirectoryHL/assets/99328320/dd1d99dc-b7b0-44c5-88e1-c6b6a661fe03)
## Summary
In this project, Vmware was used to simulate a corporate environment consisting of a client machine (Win 10), domain controller hosting Active Directory (Win Server 2019), as well as other network services needed to segment the network (NAT/RAS, DNS, DHCP). A custom Powershell script was used to create 1000 fictional users each given a username and password for clients to access the environment. Active directory was then leveraged to create Organizational Units, Group Policies, and Security groups to structure, centralize and manage user accounts, computers, and other network resources within the simulated corporate environment.

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

### Step 1: Install Windows Server 2019
- Download the Windows Server ISO file from the Microsoft website.
- Install Windows Server on the dedicated machine, following the on-screen instructions
![Screenshot 2023-06-15 021225](https://github.com/emeka789/images/assets/99328320/345c7588-71a1-4a54-97e6-a37ffd52d371)
- Perform initial configurations like setting the language, time zone, and administrator password.

### Step 2: Configure the Domain Controller
- Assign a static IP address, subnet mask, & DNS to the domain controller machine.
![Screenshot 2023-06-19 130514](https://github.com/emeka789/images/assets/99328320/447b41a0-4bd5-41ee-aa30-b8a75851a658)
- Install the Active Directory Domain Services (AD DS) role on the Windows Server.
![Screenshot 2023-06-20 023837](https://github.com/emeka789/images/assets/99328320/3f10e8ea-a509-4220-811e-d10eac8356a7)
- Promote the server to a domain controller by creating a new forest and domain.
- Configure DNS and DHCP services on the domain controller machine.
- Create user accounts, groups, and organizational units (OUs) as needed.
![Screenshot 2023-06-20 030134](https://github.com/emeka789/images/assets/99328320/cd5d4542-186a-4df7-9765-382e19ff42f9)

### Step 3: Install the Client Machine
- Install the appropriate version of Windows client OS on the client machine.
- Join the client machine to the domain created in Step 2.
- Configure network settings on the client machine to ensure connectivity with the domain controller.
![Screenshot 2023-06-20 031608](https://github.com/emeka789/images/assets/99328320/7483dbbe-de72-40b9-b033-8880cb35f361)

### Step 4: Test the Domain Controller and Client Connection
- Log in to the client machine using a domain user account.
- Verify domain user permissions and access to shared resources.
- Perform basic tests like pinging the domain controller and accessing network shares.
![Screenshot 2023-06-20 031927](https://github.com/emeka789/images/assets/99328320/f7def568-94e3-4f49-aa13-a88ded8341f4)
![Screenshot 2023-06-20 031830](https://github.com/emeka789/images/assets/99328320/9f5d211d-1aee-4c4d-aba2-d4b78201c956)

### Step 5: Additional Considerations (optional)
- Configure Group Policies to enforce security settings and apply specific configurations.
- Set up file sharing and folder redirection for centralized file storage and access.
- Integrate additional services such as DNS, DHCP, or Certificate Authority to enhance the home lab setup.

## Conclusion
Congratulations! You have successfully set up a home lab with a domain controller and client machine. This environment will enable you to learn, test, and experiment with various networking and security configurations. Feel free to explore further possibilities and expand your home lab setup.

