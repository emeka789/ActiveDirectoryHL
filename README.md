# Building an Integrated Home Network with Centralized User Authentication

This repository contains a step-by-step guide on setting up a home lab network with a domain controller and client machine. The guide provides detailed instructions and configurations to help you create your own home lab environment.

## Table of Contents
- [Introduction](#introduction)
- [Tools Used](#tools-used)
- [Installation and Configuration](#installation-and-configuration)
  - [Step 1: Install Windows Server](#step-1-install-windows-server-2019)
  - [Step 2: Configure the Domain Controller](#step-2-configure-the-domain-controller)
  - [Step 3: Install the Client Machine](#step-3-install-the-client-machine)
  - [Step 4: Test the Domain Controller and Client Connection](#step-4-test-the-domain-controller-and-client-connection)
  - [Step 5: Additional Considerations](#step-5-additional-considerations-optional)
- [Conclusion](#conclusion)

## Introduction
This guide demonstrates how to set up a home lab environment with a domain controller and client machine. By creating a domain controller, you can centralize user management and resource access control, providing a more organized and secure network for your home lab.

## Tools Used
- Vmware (or any virtualization technology)
- Windows Server 2019
- Powershell (bulk user account provisioning)
- Client Machine (Windows 10)

## Installation and Configuration

### Step 1: Install Windows Server 2019
- Download the Windows Server ISO file from the Microsoft website.
- Install Windows Server on the dedicated machine, following the on-screen instructions
- Perform initial configurations like setting the language, time zone, and administrator password.

### Step 2: Configure the Domain Controller
- Assign a static IP address to the domain controller machine.
- Install the Active Directory Domain Services (AD DS) role on the Windows Server.
- Promote the server to a domain controller by creating a new forest and domain.
- Configure DNS and DHCP services on the domain controller machine.
- Create user accounts, groups, and organizational units (OUs) as needed.

### Step 3: Install the Client Machine
- Install the appropriate version of Windows client OS on the client machine.
- Join the client machine to the domain created in Step 2.
- Configure network settings on the client machine to ensure connectivity with the domain controller.

### Step 4: Test the Domain Controller and Client Connection
- Log in to the client machine using a domain user account.
- Verify domain user permissions and access to shared resources.
- Perform basic tests like pinging the domain controller and accessing network shares.

### Step 5: Additional Considerations (optional)
- Configure Group Policies to enforce security settings and apply specific configurations.
- Set up file sharing and folder redirection for centralized file storage and access.
- Integrate additional services such as DNS, DHCP, or Certificate Authority to enhance the home lab setup.

## Conclusion
Congratulations! You have successfully set up a home lab with a domain controller and client machine. This environment will enable you to learn, test, and experiment with various networking and security configurations. Feel free to explore further possibilities and expand your home lab setup.

