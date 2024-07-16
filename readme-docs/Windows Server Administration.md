# Windows Server Administration

## Microsoft Active Directory

This section functions as an exhaustive guide delineating our strategic approach to harnessing the capabilities of Active Directory, elucidating the meticulous procedures we have undertaken to establish a resilient and secure directory service within our organisation. The implementation of Active Directory is paramount in our pursuit of constructing a centralised and methodically organised network, proficiently managing user accounts, facilitating seamless resource access, and ensuring a secure and scalable operational environment.
In an unwavering commitment to fortifying data security, we have instituted stringent measures to mitigate potential threats proactively, safeguard sensitive information, and uphold the integrity of our systems. Our adoption of a dual-server approach underscores our steadfast dedication to delivering a seamless and secure digital ecosystem.

A dedicated PC setup has been established within each cafe to address the operational requisites of our branch managers, particularly those overseeing our cafe outlets. Leveraging a secure Virtual Private Network (VPN) connection, these branch managers can seamlessly access the central file server located at the head office. This robust infrastructure enables the swift retrieval of Point-of-Sale (POS) materials and other critical information, fostering a cohesive and responsive network environment.

### AD Installation

Active Directory Domain Services (AD DS) is a critical component in Windows Server environments, and several vital functionalities and benefits underscore its importance.

The [Installation Video](https://www.youtube.com/watch?v=k5VWd_0uTiQ&t=0s) documents the steps to ensure the AD DS runs correctly.

### Demonstrating Our Active Directory Setup:

This section is designed to walk you through the step-by-step process of setting up our Active Directory domain, "4GuysCoffee." From initial planning to the execution of domain controllers and the configuration of essential AD components, this document will serve as a comprehensive reference and gain you insights into the meticulous planning and implementation of our Active Directory setup and the measures we've taken to fortify our network against potential security vulnerabilities. Thank you for being part of this crucial initiative at 4GuysCoffee!

#### Active Directory Installation

[![Alt text](https://img.youtube.com/vi/k5VWd_0uTiQ/0.jpg)](https://www.youtube.com/watch?v=k5VWd_0uTiQ&t=0s)

Active Directory Domain Services (AD DS) is a critical component in Windows Server environments, and its importance is underscored by several key functionalities and benefits.

These are comprehensive steps that should be taken to ensure the AD DS is up and running correctly.

1. Prepare the Server:
    * Ensure the server has a static IP address.
    * Set the server's DNS to its own IP address.

2. Open Server Manager:
    * Launch Server Manager from the taskbar or Start menu.

3. Add Roles and Features:
    * Click on "Manage" and then select "Add Roles and Features."
    * Follow the wizard to select the server and add the "Active Directory Domain Services" role.

4. Configure Role Services:
    * In the "Add Roles and Features Wizard," click "Next" until the "Select server roles" page.
    * Choose "Active Directory Domain Services."
    * Follow the prompts to add required features.

5. Install AD DS:
    * Review the information and click "Install" to begin the installation.

6. Promote the Server to a Domain Controller:
    * After the installation, a notification will appear. Click on "Promote this server to a domain controller."

7. Active Directory Domain Services Configuration Wizard:
    * Choose "Add a new forest" if this is the first domain controller in the forest.
    * Enter the root domain name (e.g., 4GuysCoffee.com).
    * Set the Directory Services Restore Mode (DSRM) password.
    * Review the NetBIOS name suggestion.

8. Domain Controller Options:
    * Choose the domain and forest functional levels.
    * Configure DNS options if needed.

9. Additional Options:
    * Specify the location for the AD DS database, log files, and SYSVOL.
    * Review settings and click "Next."

10. Review Options:
    * Review the configuration settings and click "Install."

11. Complete the Installation:
    * After the server restarts, log in using the domain administrator credentials.

#### Post-Installation Steps:

1. Verify Active Directory Installation:
    * Open "Active Directory Users and Computers" to confirm the AD structure.

2. Configure DNS:
    * Verify DNS settings to ensure proper resolution.

3. Update DHCP Settings (if applicable):
    * If the network uses DHCP, update DHCP settings to point to the new domain controller for DNS.

4. Backup:
    * Regularly back up the domain controller, especially the Active Directory database.

5. In our case, we have added extra domain controllers (DC). These are the steps we took:
    * Configure the Static IP for the new PC.
    * As for DNS, make sure it is set according to the DNS address of the main DC.
    * Add AD DS and DHCP roles as per guided in previous steps.
    * Promote the new PC as a Domain Controller.
    * Flexible Single Master Operation, or FSMO roles can also be configured from the Active Directory Users and Computers tool.
    * Tip: The current FSMO roles can be determined by running this command in the command prompt
    ```sh
    netdom query fsmo
    ```
    ![Delegating Operations Masters](HTDOCS/img/dc-assignment.png)
    ![Figure showing the newly added DC](HTDOCS/img/dc-assignment2.png)


#### Adding a PC to the Server

Prerequisites
Before proceeding, make sure the following prerequisites are met:
  * The PC and Active Directory server are on the same network.
  * The PC has a valid IP address and can communicate with the Active Directory server.
  * You have administrative credentials for the Active Directory domain.

1. Access System Properties on the PC:
    * Right-click on "This PC" or "Computer" on your desktop or in the File Explorer.
    * Select "Properties" from the context menu.

2. Access System Info:
    * In the System Properties window, click on "Advanced system settings" on the left sidebar.

3. Join a Domain:
    * In the System Properties window, under the "Computer Name" tab, click on the "Change" button.

4. Enter Domain Information:
    * Select the option for "Domain" and enter the name of your Active Directory domain.
    * Click "OK."

5. Provide Credentials:
    * You will be prompted to provide credentials for an account that has permission to join computers to the domain. Enter the username and password of a domain administrator.
    * Click "OK."

6. Confirm Domain Join:
    * A dialog box will confirm the successful connection to the domain.
    * Click "OK."

7. Restart the PC:
    * You will be prompted to restart the computer to apply the changes.
    * Click "Restart Now" or restart the PC manually.

8. Log in with Domain Credentials:
    * After the restart, on the login screen, select the domain from the drop-down menu.
    * Log in using domain credentials (username and password).


#### Creating Organizational Units (OUs) and Security Groups

1. Open Active Directory Users and Computers

2. In the left pane, expand the domain node.

3. Create Organizational Unit:
    * Right-click on the domain node or an existing OU where you want to create the new OU.
    * Select "New" and then choose "Organizational Unit."

4. Enter OU Name:
    * Provide a name for the new OU and click "OK."

5. Creating Security Groups:
    * Right-click on the domain node or an existing OU where you want to create the new security group.
    * Select "New" and then choose "Group."

6. Enter Group Information:
    * Enter a name for the security group.
    * Choose the group scope (e.g., Global, Domain Local, Universal) based on your requirements.
    * Choose the group type (e.g., Security, Distribution) based on whether the group will be used for security or distribution purposes.
    * Click "OK."

7. Group Membership:
    * After creating security groups, you can manage their membership by double-clicking on the group and adding members in the "Members" tab.



#### Securing Active Directory

Ensuring the security of our Active Directory environment is of paramount importance to us. Following are the specific strategies we have implemented to harden our AD setup:

1. Group Policy Objects (GPOs) to enforce security settings such as password policies (enforce strong passwords, length of the passwords, expiration, etc), and user rights assignments.
2. Account lockout policies to limit login attempts and protect against brute-force attacks.
3. We have configured the [GPO Rules](https://youtu.be/aSS2KEWCLHo) to turn the firewalls on automatically in all of our workstations and disallow users to disable them. 
4. Inbound [Firewall Rules](https://youtu.be/vZaHpq-9_o0) allow only essential traffic to our domain controllers, limit unnecessary ports and services and implement outbound firewall rules to restrict unnecessary communication from domain controllers.
5. Implement regular updates, scanning and patching to address vulnerabilities promptly.
6. Disable SMB1 & Link-Local Multicast Name Resolution (LLMNR) via GPO.
7. Disable NetBOIS Name Service (NBT-NS) via PowerShell.
8. Utilise [non-standard port configurations](https://youtu.be/7x_JVszswqc) for Remote Desktop Protocol (RDP) to minimise attack surface.
9. Physical security measures are also in place to protect servers housing domain controllers.
10. Finally, in the context of preventing the evolving social engineering attacks and phishing attempts, we conduct security awareness training for users to prevent social engineering attacks and phishing attempts.