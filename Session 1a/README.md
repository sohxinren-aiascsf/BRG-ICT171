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

![alt text](<16. top command.png>)  
top command shows real-time system performance and running processes in the terminal that continuously refreshes screen at every 3 seconds interval instead of a snapshot like ps -e. I can quit with ‘q’, ‘p’ to sort by CPU memory, ‘k’ to kill processes by PID. Toggling ‘1’ switches between the number of CPU usage, when I created the VM with 4 CPUs, I can see Cpu0 – 3.  

![alt text](<17. list command.png>)  
ls with -xx is similar to the earlier setup to list files, different functions such as -la (long listing + all entries), -alt (all files, including hidden + long format + sort by time), -lah (long listing + all entries + human-readable sizes (KB/MB/GB instead of raw bytes)) provides different options in a chronological order.  

![alt text](<18. touch command.png>)  
Create new file using ‘touch’  

![alt text](<19. gedit command.png>)  
gedit command to open graphical text editor  

![alt text](<20. nano command.png>)  
nano command for GUI editor without full IDE  

![alt text](<21. cat command.png>)  
cat command reads files and writes them to my terminal  

![alt text](<22. less command.png>)  
Screenshot 13: less command to reading and exploring longer files which require scrolling  
gedit = GUI editor (editable)  
nano = text editor (editable)  
cat = quick glances at short files (view only)  
less = reading and exploring longer files while scrolling (view only)  

![alt text](<23. copy command.png>)
copy command  

![alt text](<24. move command.png>)  
Explored various move commands, I moved testfilebackup to Downloads folder, renamed testfilebackup to filetestbackup, attempted to rename Downloads folder but realized I was in the wrong directory, need to go back up one level before I can rename the folder to MyDownloads.  

![alt text](<31. remove file.png>)  
Removed the filetestbackup file

![alt text](<25. view system info command.png>)  
uname -a displays basic system info with all fields in one line to know the kernel version quickly.  
lsb-release -a displays Linux Standard Base and distribution specific information with all fields to know which distro and version.  
hostnamectl displays hostname information for a more detailed OS summary snapshot for the VM.  

![alt text](<26. whoami and superuser command.png>)  
whoami command and super user privilege escalation  

![alt text](<27. add new user.png>)  
Attempted to add a new user but failed because I am not in the root privilege. This shows that user management is restricted to root-level privileges. sudo is a controlled mechanism for temporarily escalating a normal account to perform administrative tasks.  

![alt text](<28. identify private IP.png>)  
Identify private IP address  

![alt text](<29. ping test.png>)  
ping local device ensures my NIC is serviceable.  
ping 8.8.8.8 tests raw IP connectivity to Google’s DNS server.  
ping google.com tests if my system have any DNS issues.  

![alt text](<30. create new alias and ping test.png>)  
Create new alias for googledns and perform ping test  

![nslookup](<32. nslookup google.png>)  
nslookup query DNS and show which IP address google.com resolves to, and which DNS server answered

![alt text](<33. whois google.png>)  
sudo apt install whois installs the whois client on to query domain registration records
whois google.com asks WHOIS registries for information about the google.com domain  

nslookup = DNS records  
whois = ownership/registration  

![alt text](<34. list usb and pci.png>)  
Lists USB buses and connected USB devices such as keyboard, mouse, webcam.  
Lists PCI devices such as network cards, storage controllers, graphics adapters, etc, useful to see what virtual hardware VirtualBox is emulating.  

![alt text](<36. cpu info command.png>)  
scroll through detailed CPU information: model, cores, threads, cache sizes, flags

![alt text](<35. redirecting output to a file.png>)  
lsusb > output_of_lsusb run lsusb, create a file with the outputs  
less output_of_lsusb opens the file in a scrollable page  
cat output_of_lsusb displays the entire file in the terminal  
ls -la output_of_lsusb shows file metadata: permissions, owner, size, timestamps, and confirms the file exists and how big it is.  

![alt text](<38. sudo apt search keyword.png>)  
sudo apt search keyword vlc  

![alt text](<39. sudo apt install vlc.png>)  
install vlc via the keyword search earlier  
instead of searching the web to download and install the correct compatible version, using this CLI command searches the apt repository for installing. very nice indeed!  

![alt text](<40. hello world executable.png>)  
after installing build-essential meta-package which includes gcc, g++, core development headers and libraries, compile the c program "Hello World!", then ./hello_world_executable tells the shell to run in the current directory, printing it out in the terminal.  

![alt text](<41. less hello_world.png>)  
opens the c program in less for scrolling  

![alt text](<42. less hello_world_executable.png>)  
opens the compiled binary file but mostly unreadable characters because it is machine code, not text.  
This exercise shows me the difference between human-readable .c file vs binary executable.  

# Reflection
In this Session, I tried several ways of distributing and installing software. From using package managers (apt), direct downloads, compiling from source, and ISO images.  

As a user, apt felt the most convenient and safest because dependencies and updates are handled for me in a single command. Direct downloads are useful when I need a newer version than the repo provides, but I have to think more about trust and manual updates from offical websites.  

Compiling from source with gcc was the unique, but it gave me a clear understanding of what is actually being built, which is valuable as a IT student.  
Using Ubuntu ISO image on my VirtualBox make it easy to get a complete, reproducible environment for labs without risking my host OS.

From a software company’s perspective, I can see why they often mix approaches. Package managers and prebuilt images reduce friction for users and support, while direct downloads and source give them more control over release timing, licensing, and community contributions. Each method trades off convenience, security, control, and maintenance effort on both sides.