# Active Directory IAM Lifecycle Simulation & Automation using Powershell
![Copy of Log ana](https://github.com/emeka789/ActiveDirectoryHL/assets/99328320/dd1d99dc-b7b0-44c5-88e1-c6b6a661fe03)
## 🎯 Summary 
The goal of the porject is to build a virtual lab using VMware and Windows Server to simulate an enterprise IT environment. This was done by configuring client machines (Win 10), a domain controller hosting Active Directory, and other network services needed to segment the network (NAT/RAS, DNS, DHCP). Active directory was then used to create organizational units (OU), group policies (GP), and security groups (SG) to structure, centralize, and manage user accounts and other network resources.

## 🛠️ Tools and Technologies Used
- Vmware
- Windows Server 2019
- Client Machine (Windows 10)
- Active Directory
- Active Directory Domain Services
- Powershell

## 🖥️ Step 1: Create Virtual Machine
#### 1.1 Create New Virtual machine
![Image](https://github.com/user-attachments/assets/9cf15001-ed0a-4050-912f-485ff8b56b8b) 

#### 1.2 Go through TYPICAL installation process and install VM
![Image](https://github.com/user-attachments/assets/b1965ca9-6af1-4b14-841e-a28592036b81)

## 🛠️ Step 2: Install Windows Server 2019 
#### 2.1 Start VM & Install OS
![Image](https://github.com/user-attachments/assets/096bfc48-eee6-405f-a959-0d35aa248888)

## 🧰 Step 3: Install Active Directory
#### Start --> Server Manager --> Add Roles and Features
#### Before you begin --> Next 
#### Role-based or feature-based installation & Server Selection --> Next
#### Server Roles --> Check Active Directory Domain Services ✅
#### Features --> Next --> Next ✅
![Image](https://github.com/user-attachments/assets/294acb47-b0ce-4445-9427-7955ab1938c8)
![Image](https://github.com/user-attachments/assets/018c54c7-b388-45ef-9ebe-1935e8d596ec)
#### Install! ✔️

## 🫂 Step 4: Create Users in Active Directory with PowerShell
#### 4.1 Create text file with list of names of users
![Image](https://github.com/user-attachments/assets/c6adfb67-c241-406b-bcf5-41c67c07ac44)
#### 4.2 Use this [Powershell](https://github.com/joshmadakor1/AD_PS/blob/master/Generate-Names-Create-Users.ps1) script to add new users from text file to Organizational Unit --> USERS
![Image](https://github.com/user-attachments/assets/4be3eb9a-2430-4af2-85e0-fa0417bf073b)
#### 4.3 Users have now been added to Organizational Unit 🥳
![Screenshot 2023-06-10 183311](https://github.com/emeka789/ActiveDirectoryHL/assets/99328320/74b3dcd0-4668-4ba3-80dd-ce7b608f6026)
### After creating users, let's manage what resources have access to 🪨
## Step 5: Configure Role-Based Access Control (RBAC) with Security Groups
#### 5.1 Update CSV file
To automate Group Assignments using Powershell, you can update the text file to include categories for example...
#### First Name, Last Name, Username & Department
#### 5.2 Use this script in Powershell to add users to their specified Group
`
Ps C:\Users\Administrator> Import-Csv "C:\Users\Administrator\Desktop\names/txt | ForEach-Object {
  $username = $_.Username
	$group = $_.Department + "_Group"
	Add-ADGroupMember -Identity $group -Members $username
}
`
#### 5.3 Run Script & verify group membership
![Image](https://github.com/user-attachments/assets/0c72bc58-8391-47d2-ba77-167171962050)
## 👮 Step 6: Apply Group Policy Objects & Simulate User Offboarding
#### 6.1 Apply Group Policy Object to restrict access to the Control Panel
##### Open Group Policy Management from Start Menu -> Expand `lab.local > Domains > lab.local`
##### Right Click lab.local & Select "Create a GPO in this domain and Link it here"
##### Name it: Disable_ControlPanel_IT
##### Right click new GPO -> Edit -> User Configuration -> Policies -> Administrative Templates -> Control Panel
##### Select "Prohibit access to Control Panel and PC Settings" & Enable
![Image](https://github.com/user-attachments/assets/9205bf56-aa49-4724-8363-23df61c6eb81)
##### Choose OK! ✅
#### 6.2 Target the GPO to the USER Group only

The following roles and services for Active Directory and the Domain Controller were configured
![286363729-25d70bde-a64a-4de3-bf8d-4ade4bd69542](https://github.com/emeka789/ActiveDirectoryHL/assets/99328320/2b2684f2-b08e-4e7b-a9ca-bc6db37f2534)

![Screenshot 2023-06-10 122014](https://github.com/emeka789/ActiveDirectoryHL/assets/99328320/20edc126-173a-42b0-ac63-6ba445a0f5ec)



## Joining Client Machine (Win 10) to the Domain
For this, a Windows ISO image was used to install the Windows 10 operating system on the VMware virtual machine with the Network Adapter set to internal to ensure all network traffic flows through the domain controller. An account was created to access the machine and connected to mydomain.com pinged to verify the connection. The connection was verified by logging in with credentials of users created using the Powershell script.


![Screenshot 2023-06-20 031927](https://github.com/emeka789/images/assets/99328320/f7def568-94e3-4f49-aa13-a88ded8341f4)
![Screenshot 2023-06-20 031830](https://github.com/emeka789/images/assets/99328320/9f5d211d-1aee-4c4d-aba2-d4b78201c956)

![Screenshot 2023-06-11 205123](https://github.com/emeka789/ActiveDirectoryHL/assets/99328320/6d79402f-773a-4146-a3de-81493dfaf4f6)

The same process can be used to log in to additional users created using mulitple VMs. Within the DC, Active Directory was checked to see if client populated correctly.

![Screenshot 2023-06-12 175138](https://github.com/emeka789/ActiveDirectoryHL/assets/99328320/dfa7f250-7995-4220-b33d-0f8432b9922c)


![Screenshot 2023-06-20 031608](https://github.com/emeka789/ActiveDirectoryHL/assets/99328320/d56b7c86-48e2-42ec-9d84-7e447dacfb09)
