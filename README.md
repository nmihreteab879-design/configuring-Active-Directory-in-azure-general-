<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

# Active Directory Deployment

This project covers installing Active Directory, creating the domain structure, setting up admin and user accounts, and joining a workstation to the domain. Instead of documenting every single click, this write-up focuses on the key configurations that matter in real environments—identity management, permissions, domain structure, and workstation integration.

## Environments and Technologies Used
- Microsoft Azure (Virtual Machines)
- Remote Desktop Protocol (RDP)
- Windows Server Manager
- Active Directory Users and Computers (ADUC)
- PowerShell

## Operating Systems Used
- Windows Server (Domain Controller)
- Windows 10 (Client Machine)

## Objectives
- Install and configure Active Directory Domain Services  
- Build an organized domain with proper OUs  
- Create administrator accounts following security best practices  
- Join Windows devices to the domain  
- Configure workstation access for domain users  
- Automate bulk user creation with PowerShell  

# Core Deployment Overview

## Installing Active Directory on DC-1  
<img width="785" height="564" alt="image" src="https://github.com/user-attachments/assets/e402d1ee-2c2a-495e-a278-2f09742a56d5" />


Why this matters:  
This step turns a normal Windows Server into the central identity system for the entire network. Every login, permission, computer object, and security policy depends on the domain controller being set up correctly.


Skills demonstrated:  
• Installing AD DS  
• Creating a new domain/forest  
• Promoting a server to a domain controller  


## Creating Admin and Employee OUs  
<img width="758" height="529" alt="image" src="https://github.com/user-attachments/assets/bd08954f-a039-4042-a1f3-47fe05f491cb" />


Why this matters:  
Without organization, companies with hundreds or thousands of users become impossible to manage. OUs keep accounts structured so policies, permissions, and security rules can be applied cleanly.


Skills demonstrated:  
• Designing and organizing OUs  
• Structuring user accounts for long-term management  
• Understanding how AD separates groups of users  

## Creating a Domain Admin Account (jane_admin)  
<img width="412" height="533" alt="image" src="https://github.com/user-attachments/assets/e90c7103-0b1b-4919-aaad-c8316655d012" />
<img width="409" height="536" alt="image" src="https://github.com/user-attachments/assets/16ebce72-f26f-457a-a2eb-756557d9ef96" />
<img width="757" height="530" alt="image" src="https://github.com/user-attachments/assets/0b0385d2-d128-4481-bc69-d0df8f1225a3" />


Why this matters:  
Administrators should not use the built-in Administrator account day-to-day. Creating a proper domain admin account follows real-world security best practices and prevents misuse of privileged access.


Skills demonstrated:  
• Creating domain users  
• Assigning admin privileges through groups  
• Logging in with proper elevated credentials  


## Joining Client -1 to the Domain  
<img width="328" height="419" alt="image" src="https://github.com/user-attachments/assets/08a7f1c4-1c9a-47eb-95aa-7cbe018e3e58" />
<img width="754" height="528" alt="image" src="https://github.com/user-attachments/assets/c59dc5cd-68bb-410a-8f87-b799c187f9d8" />


Why this matters:  
Joining a machine to the domain gives IT full control over it—policies, updates, authentication, and security. If this step isn’t done correctly, users can’t log in or receive company policies.


Skills demonstrated:  
• Joining Windows devices to a domain  
• Configuring DNS for domain communication  
• Verifying computer objects in ADUC  
• Moving devices into proper OUs  
 

## Allowing Remote Desktop for Domain Users  
<img width="1201" height="935" alt="image" src="https://github.com/user-attachments/assets/d337c333-e400-41e1-b47b-d902a570d9ec" />
<img width="1204" height="935" alt="image" src="https://github.com/user-attachments/assets/2fc2614d-6447-4fe5-ba64-86622fe716ec" />



Why this matters:  
Companies often require remote access for employees. Setting this correctly ensures users can connect without giving them full admin privileges, which keeps the environment secure.


 Skills demonstrated:  
• Configuring local RDP permissions  
• Managing domain user access on client machines  
• Understanding device-level access control  


 ## Bulk User Creation with PowerShell  
<img width="1536" height="954" alt="image" src="https://github.com/user-attachments/assets/ae34ad41-0f03-4dbb-b2fb-609ccc084b0f" />


 Why this matters:  
Sometimes companies need to create many accounts at once. Doing it manually would take too long and increase the chance of mistakes. Using PowerShell to automate the process shows that you can handle bulk tasks quickly and accurately.


  Skills demonstrated:  
• Running basic PowerShell scripts  
• Creating multiple users from a CSV file  
• Placing new accounts in the correct OU  
• Following consistent naming and account standards

## summary 

In this project, I installed and configured Active Directory, created an organized domain structure, set up a proper admin account, joined a workstation to the domain, enabled user access, and used PowerShell to automate bulk user creation. Overall, this shows I can build and manage the core pieces of a Windows domain environment using real IT practices.

