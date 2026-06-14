# Session 1a

![alt text](<1. VirtualBox Installed.png>)  
VirtualBox Installed  

![alt text](<2. Ubuntu ISO Downloaded.png>)  
Download Ubuntu ISO from official website

![alt text](<3. New VM Created.png>)  
Create New VM  

![alt text](<4. Ubuntu_Installed.png>)  
Install Ubuntu  

![alt text](<5. Networking Mode Bridged.png>)  
Set up Bridged Network between VM and Host  

![alt text](<6. Check Internet in Ubuntu.png>)  
Check Internet Access in Ubuntu  

![alt text](<7. sudo apt upgrade -y.png>)  
Upgrade packages  

APT (Advanced Package Tool) is Ubuntu’s package management layer that handles installation, upgrading, and removing software.  
A repository is a remote collection of packages, for this assignment, I am using GitHub as a blog to document my learning.  
Differences between sudo update and upgrade, apt update refreshes package lists, no software will be installed, only the local index is updated, whereas apt upgrade installs newer versions of currently installed packages based on the index. I noticed that for my upgrade of Ubuntu, google-chrome takes up a significant amount of time.  

![alt text](<8. basic commands.png>)  
pwd and ls  
Basic commands such as pwd “prints working directory” displays the filesystem root to my current directory. It lets me confirm my exact location which is extremely helpful after many cd “change directory” jumps where I might get lost. This is an important and good habit to run pwd command before creating, moving, or deleting files so I do not accidentally touch the wrong directory. ls is a command to list out the contents of a directory.  

![alt text](<9. ip a command.png>)  
ip a command shows my current network details such as ip address and MAC address.  

![alt text](<37. ping and hostname change.png>)  
ping google.com tests my machine if it can reach Google’s server over the network and measures latency using ICMP echo requests. Pressing Ctrl + C stops the ping, similar to pinging in command prompt in Windows environment.  

![alt text](<10. enabling ssh.png>)  
Enabling ssh allows my VM to be accessed from my host OS for bridged network setup. I need to ensure that the service is “active”.  

![alt text](<11. Fedora exploration1.png>)  
![alt text](<12. Fedora exploration2.png>)  
![alt text](<13. Fedora exploration3.png>)  
![alt text](<14. Fedora exploration4.png>)  
I explored Fedora VM in a separate VM with basic commands used in Ubuntu. The commands are similar, dnf is used instead of apt to update/upgrade installation packages.  

Overall Reflection for initial setup:  
The advantages of using VM for testing and development provide isolation and safety as each VM is sandboxed, so crashes, malware that occur in my VM do not affect my host OS. I can also create multiple clean environments for testing, especially if I want to test different OS versions and configurations without extra hardware. Using VM provides me flexibility in resources as I can tune my CPU/RAM/disk per VM and reuse preconfigured images, reducing time spent re-installing and reconfiguring systems.  

There were not many challenges faced during the initial setup, other than the longer than expected waiting time to update google chrome from “sudo apt upgrade -y” command. Linux commands are somewhat similar to command prompt commands, so I can draw some correlation between them.  

Initially, my VM could reach the internet but I could not SSH from my host OS. I later realized that my VM was using NAT instead of Bridged, so I had an internal IP address that my host OS could not reach directly. I shutdown my VM, reconfigured my Ubuntu Network settings to Bridged to rectify. From this occurrence, I understood that NAT is like putting the VM behind a virtual router, able to access outbound, restricted inbound. Bridged makes my VM like a full machine on the physical network to perform bi-directional testing.  

Using VirtualBox, I observed that different Linux distributions have similar commands, but ‘apt’ in Ubuntu becomes ‘dnf’ in Fedora for package installation. I just explored around the simple commands such as pwd, ls, ip a, ping and hostname change in Fedora for a simple “feel-the-difference” experience.  

hostname displays my machine’s name. sudo hostnamectl set-hostname, adding a ctl at the back of command provides control in changing the hostname of my machine.  

![alt text](<15. process monitoring.png>)  
Monitor processes using ps -e (ps = process, e = everything).  


























![nslookup](<32. nslookup google.png>)  
nslookup query DNS and show which IP address google.com resolves to, and which DNS server answered

