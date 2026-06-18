# Session 2b

✅ 1	EC2 Instance Launched	Screenshot of the EC2 dashboard showing the instance running (state = running), with Ubuntu 20.04, free tier eligible, and security group configured.
![alt text](<EC2 Dashboard 2-1.png>) ![alt text](<EC2 Dashboard-1.png>)

✅ 2	Security Group Configured	Screenshot showing inbound rules: 
• Port 22 (SSH) 
• Port 80 (HTTP) opened
![alt text](Security-1.png)

✅ 3	SSH Access Successful	Terminal output showing successful SSH login using the .pem key. Example: ssh -i "yourkey.pem" ubuntu@<public_dns>
![alt text](<Powershell ssh-1.png>)

✅ 4	Apache Installed and Tested	Output of sudo apt install apache2 and browser screenshot of the Apache welcome page (http://<http://32.236.223.226/>)
![alt text](<Apache welcome page cloud-1.png>)

✅ 5	Custom index.html Edited	Edited /var/www/html/index.html with personalized content. Screenshot of the file content (nano or gedit) and browser output
![alt text](<Apache welcome page cloud nano edited-1.png>)
![alt text](<Apache welcome page cloud edited-1.png>)

✅ 6	External File Downloaded with wget	Screenshot of successful download using wget, e.g., wget http://...EECS-2009-28.pdf, saved in /home/ubuntu
![alt text](<external file downloaded-1.png>)
![alt text](<file saved-1.png>)

✅ 7	File Copied to Web Root	Screenshot of sudo cp command copying a file to /var/www/html, and ls -l output showing it there with correct permissions
![alt text](<copy to root-1.png>)

✅ 8	PDF File Accessible via Browser	Screenshot of downloading or viewing http://<public_ip>/EECS-2009-28.pdf from browser or mobile
![alt text](<access pdf file-1.png>)

✅ 9	Link Inserted in HTML Page	index.html edited with a hyperlink to the PDF file. Screenshot of HTML snippet: <a href="EECS-2009-28.pdf">Click here</a> and visible link in browser
![alt text](<click here pdf-1.png>)

✅ 10	Budget Monitoring Enabled	Screenshot of AWS Billing Dashboard with budget alert setup or cost summary
![alt text](billing-1.png)

✅ 11	Instance Terminated (Optional)	Screenshot of EC2 instance terminated or stopped, showing awareness of cost management
![alt text](<instance stopped-1.png>)

✅ 1	Directory and File Operations Completed	Screenshot or terminal output of:
• mkdir LabFiles
• Creating notes.txt
• Using cat, cp, mv, rm to manipulate files
![alt text](<bash 1-1.png>)

✅ 2	Reflection: File System Commands	Written answers to:
• What command did you use to create a directory? mkdir LabFiles
• How can you view file content without a GUI editor? cat notes.txt (quick concantenated view)
• What is the difference between cp and mv? cp = copy, mv = move

✅ 3	Basic Bash Script Created and Run	Evidence of:
• hello_world.sh script created with #!/bin/bash and echo line
• chmod 777 hello_world.sh
• Output of script execution showing custom message
![alt text](<bash 2-1.png>)

✅ 4	Reflection: Script Basics	Answers to:
• What is chmod +x for? it makes the file as an executable so it can be run as a program using ./hello_world.sh
• Why is #!/bin/bash used? it is the command to tell the system to run the script with the Bash shell
• How can you personalize script output? change the echo message

✅ 5	Loop and Conditional Script	Screenshot or output of system_info.sh:
• Displays user with whoami
• Iteration loop from 1–5
• Input number with if-elif-else logic and validation
![alt text](<system info bash-1.png>)

✅ 6	Reflection: Loops and Conditionals	Written responses:
• How does the for loop work? it repeats the block of commands
• What happens if number > 10? it depends on the if/elif/else logic, the script will print "Number out of range."
• How could invalid input be handled more gracefully? print a clear error message, and prompt user if want to input again or exit

✅ 7	System Monitoring Script Created and Run	Screenshot or terminal output of:
• resource_monitor.sh looping through system checks:
• top, free -h, and df -h outputs shown
![alt text](<resource monitoring-1.png>)
![alt text](top-1.png)
![alt text](<free -h and df -h-1.png>)

✅ 8	Reflection: Monitoring Automation	Answers to:
• What does free -h show? it displays total used and RAM in readable units (KB, MB, GB)
• How can this script be modified to monitor network usage? add commands like ip -s link, sar -n DEV or ifstat, and sleep to collect and display network traffic perioidically.
• Why is automation important for admins? Automation reduces human error, saves time on repetitive tasks, ensures monitoring and maintenance jobs run consistently without human supervision.
