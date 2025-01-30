# Linux-management
# 2025-01-19
- Bikas Basyal, amk1002350@student.hamk.fi

# Task
How to create a virtual machine to used Azure Platform for Linux Management Course.

- Step 1: At first, I create a Azure account from portal.azure.com for myself using my university email. 


![Azure View after login ] 
![alt text](<Screenshot (2)-1.png>)

- Step 2: I created a new resource group  and new virtual machine in Azure portal.

- Step 3: I selected North Europe as a Region and Ubuntu Server 24.04 LTS - x64 Gen2 as the operating system. 

- Step 4: I selected the virtual machine size as Standard_B2ls_v2- 2 vCPUs, 4 GiB Memory ($33.29/month).

- Step 5: I selected the network configuration as Public IP address and Network interface and created a new Username (b_kas).

- Step 6: I seleceted OS disk type as Standard SSD and Storage type as Locally-redundant storage.

- Step 7: I selected the public IP address as Static and created a new public IP address as lab-robotics-ip.

- Step 8: I selected inbound ports as (Http(80), HTTPS(443), SSH(22))

- Step 9: I selected the Enable auto-shutdown and set the auto-shutdown time as 2:00 AM and Select the time Zone as (UTC + 3:00) Helsinki

- Step 10: I reviewed the settings and created the virtual machine.

After creating the virtual machine, I go to lab-robotics-ip and select setting(Configuration) than type bkas-lab-robotics as DNS name lable and save it.

- Step 11: After that, I select lab-robotics and select connect and select Native SSH and copy the path that I downloaded the key.pam file.


- Step 12: I open the terminal and paste the URL given in SSH to VM with specified private key.

![Successfully done in Terminal ]
![alt text](<Screenshot (1)-1.png>) 


# Creating Users Tupu (Using) To create the user tupu, use the following command: 
         sudo adduser tupu

This will:
1.Create a new user tupu.

2.Automatically create the home directory /home/tupu.

3.Set the default shell to /bin/bash.

4.Prompt for password creation and additional user details.

 # Tupu (Using) To create the user lupu, use the following command:

            sudo useradd -m -d /home/lupu -s /bin/bash -G lupu lupu

This will:

1.Create the user lupu

2.Set the home directory to /home/lupu

3.Assign the default shell /bin/bash

4.Add lupu to the lupu group            

# Set a password for lupu:

            sudo passwd lupu


Hupu (System User) To create a system user hupu with restricted login, use:            

            sudo useradd --system --shell /bin/false hupu

Granting Sudo Privilege Method 1: Using (Recommended) Edit the sudoers file safely:  
                sudo visudo  

Method 2: Adding Users to the Group Alternatively, run:

                sudo usermod -aG sudo tupu
                sudo usermod -aG sudo lupu

Verify with:

            groups tupu
            groups lupu

3.Setting Up Shared directory Step 1: Create the directory

         sudo mkdir /opt/projekti

Step 2: Create and Assign a Group

            sudo groupadd projekti
            sudo usermod -aG projekti tupu
            sudo usermod -aG projekti lupu

Step 3: Set Directory Ownership

            sudo chown :projekti /opt/projekti

Step 4: Set Permissions

            sudo chmod 770 /opt/projekti

Step 5: Ensure New Files Inherit Group Ownership

            sudo chmod g+s /opt/projekti

This ensures that new files in /opt/projekti inherit the projekti group

4.Verification Check user groups:

             groups tupu
             groups lupu

Check directory permissions

            ls -ld /opt/projekti





# screenshot
![alt text](<Screenshot (4)-1.png>)
