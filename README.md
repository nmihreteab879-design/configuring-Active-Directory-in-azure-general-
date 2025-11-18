<p align="center">
  <img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>


On-Premises Active Directory Post-Install Configuration


This lab shows how I finished setting up Active Directory after the initial network and VMs were created. Tasks include promoting the server to a domain controller, creating administrative users and organizational units, joining a client to the domain, enabling remote desktop for normal users, and using a script to bulk-create employee accounts. Each section lists exactly what screenshot to include and why it matters.


Environments and technologies used
- Microsoft Azure (VMs & Networking)
- Remote Desktop (RDP)
- Active Directory Domain Services (AD DS)
- PowerShell
- Windows Server 2022 (DC-1)
- Windows 10 (Client-1)


Step: Install Active Directory Domain Services on DC-1
Screenshot to include:
- Server Manager showing "Add roles and features" with Active Directory Domain Services selected
What this shows and why it matters:
This is the step that turns a regular server into a domain controller, the machine that will manage users, computers, and permissions for the network. It shows you can install core server roles.


Step: Promote DC-1 to a Domain Controller and create the domain
Screenshot to include:
- "Promote this server to a domain controller" wizard with the new domain name (mydomain.com) visible
- Post-reboot: Windows login showing domain user (mydomain\labuser)
What this shows and why it matters:
Promoting creates the actual domain where accounts and devices live. The domain name is the namespace everything uses to find and authenticate against the controller.


Step: Create organizational units (_EMPLOYEES, _ADMINS)
Screenshot to include:
- Active Directory Users and Computers (ADUC) showing OUs named _EMPLOYEES and _ADMINS
What this shows and why it matters:
OUs are folders that help organize users and computers. They make administration scalable and tidy.


Step: Create a domain admin user (jane_admin) and add to Domain Admins
Screenshot to include:
- New user creation screen for jane_admin
- jane_admin shown as member of the Domain Admins group
What this shows and why it matters:
Creating an admin user demonstrates account provisioning and group membership control. Using a domain admin account for daily admin tasks is how domains are managed.


Step: Join Client-1 to the domain and verify in ADUC
Screenshot to include:
- On Client-1: System > Change settings > "Member of Domain mydomain.com" (or the Domain join dialog)
- On DC-1: ADUC showing Client-1 computer object
What this shows and why it matters:
Joining a device lets the domain manage it. Verifying the computer object in ADUC confirms the join succeeded.


Step: Create _CLIENTS OU and move Client-1 into it
Screenshot to include:
- ADUC showing _CLIENTS OU and Client-1 moved under it
What this shows and why it matters:
Organizing computers into an OU is how you apply group policies and manage machines at scale.


Step: Enable Remote Desktop for domain users on Client-1
Screenshot to include:
- Client-1 System properties > Remote Desktop settings showing "Allow remote connections" and Domain Users (or "Remote Desktop Users") allowed
What this shows and why it matters:
Allowing domain users remote access demonstrates how to grant safe access to non-admin staff. In production you'd typically use Group Policy for this.


Step: Create many users via PowerShell script
Screenshot to include:
- PowerShell ISE open with the user-creation script visible
- PowerShell output showing users being created
- ADUC showing the new users inside _EMPLOYEES
What this shows and why it matters:
Automation via PowerShell scales user creation and reduces errors. This shows scripting and bulk provisioning skills.


Step: Test login with a newly created user
Screenshot to include:
- Windows login screen on Client-1 with a new user signing in (use the password defined in the script)
What this shows and why it matters:
Logging in confirms that account creation, replication, DNS, and domain join are all functioning end-to-end.


Skills demonstrated (explained simply)
- Installing and configuring Active Directory services on a server
- Promoting a server to a domain controller and understanding why a stable IP and DNS are required
- Creating and organizing users, groups, and OUs to keep administration manageable
- Joining client machines to a domain and validating the join in ADUC
- Enabling controlled remote access for non-admin users
- Using PowerShell to automate repetitive administrative tasks
- Verifying the environment with basic troubleshooting (logins, ADUC visibility, DNS checks)

Notes
- Use sensible screenshot filenames and replace each placeholder image link with the actual image path in your repo.
- Do not delete the VMs after finishing; stop them in the Azure portal to save cost if you are done for the day.

