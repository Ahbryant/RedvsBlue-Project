# RedvsBlue-Project
Red vs Blue project originally created for the UT Austin Cyber Security Bootcamp


Project Description:

In this Project I'm working not only as a Red Team pentration tester but also as the Blue Team's SOC Analyst.
In this project as a Red team member I was successfully able to attack the Blue Team's vulnerable Virtual Machine; through a proccess of priviledge escaltion starting as someone who was attacking just a website using SQL Injections I rose up to gaining root access.
On the Blue side, I used Kibana as my main asset to review logs from the attack and turn those logs in to hard data and visulizations to aid in my report which included strategies for mitigation.


Project Objectives:

In this project I used knowledge and information pertaining to:
-Penetration testing using a Kali Linux os
-Log and incident analysis with Kibana
-System hardening and configuration
-Reporting, documentation, and communication


Lab Environment:

Windows Azure Lab Services 

Before the attack my object was to set up Kibana so I could capture my attack and then go back over it when I joined the blue team. Here are the commands I ran to set up Kibana:
Filebeat:
	filebeat modules enable apache
	filebeat setup
Metricbeat:
	metricbeat modules enable apache
	metricbeat setup
Packetbeat:
	packetbeat setup
Restarted the system to make sure the changes are operational:
	systemctl restart filebeat
	systemctl restart metricbeat
	systemctl restart packetbeat

Red Team Instructions:

 -Discover the IP address of the Linux web server
 -Locate the hidden directory on the web server
 -Brute force the password for the hidden directory using Hydra
 -Break the hashed password with the Crack Station website or John the Ripper
 -Connect to the server via WebDAV
 -Upload a PHP reverse shell payload
 -Execute payload to open up a meterpreter session
 -Find and capture the flag



Blue Team:

On blue team I flipped the script on myself. I used Kibana logs that I setup to monitor my own attack. This data is used in some of the pictures attached under the blue team pictures folder.
With this data I was about to set up alerts and thresholds for those alerts to monitor for future attacks.

On this side it was intersting to see how my attack was logged with Kibana. I saw the spikes from the brute forcing, the SQL injection, and the searching I did for the secret file.
Not all tactics used got picked up and that was the real eye opener. Seeing what is picked up and what isn't.

Regardless using the search bar and discover screen provided by Kibana and packetbeat I was able to complete the following objectives:

 -Identify the offensive traffic 
 -Find the request for the hidden directory 
 -Identify the brute force attack 
 -Find the WebDAV connection 
 -Identify the reverse shell and meterpreter traffic 
