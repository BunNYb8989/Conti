# Conti_Ransomware
RANSOMWARE LAB by Tryhackme

This challenge involves Splunk to investigate an Exchange server that was compromised . By the Conti ransomware. At of the lab we learn how the attackers compromised the server.

<p align="center">
<b>Root User</b>
<br/>
  <img src="Screenshot 2024-11-08 120457.png"/>
<br/>
<br/>
</p>

# SIEM TOOL SPLUNK
Splunk log analysis
- patten detection and recognition
- index=* | top limit=100 Image
- index=*  Image="c:\\Users\\Administrator\\Documents\\cmd.exe" Hashes="MD5=290C7DFB01E50CEA9E19DA81A781AF2C,SHA256=53B1C1B2F41A7FC300E97D036E57539453FF82001DD3F6ABF07F4896B1F9CA22,IMPHASH=23F815785DB238377F4513BE54DBA574"
- index=* EventCode=11 Image="c:\\Users\\Administrator\\Documents\\cmd.exe"
- index=* 4720
- index=* sourcetype="WinEventLog:Microsoft-Windows-Sysmon/Operational"
- index=* sourcetype="WinEventLog:Microsoft-Windows-Sysmon/Operational" EventCode=8 TargetImage="C:\\Windows\\System32\\lsass.exe"
-  
-  

# Task 1
Some employees from your company reported that they can’t log into Outlook. The Exchange system admin also reported that he can’t log in to the Exchange Admin Center. After initial triage, they discovered some weird readme files settled on the Exchange server.  (ransomware note which is readme.file --conti(ransom))
<p align="center">
<b>Root User</b>
<br/>
  <img src="TASK_1.png"/>
<br/>
<br/>
</p>
CLICK on Complite (for task 2)

# Task 2
<p align="center">
<b>Root User</b>
<br/>
  <img src="TASK_2.png"/>
<br/>
<br/>
</p>

Microsoft Exchange Server: is a mail server and calendaring server developed by Microsoft. It runs exclusively on Windows Server operating systems and is designed to manage various forms of digital communication within an organization

Exchange Server integrates seamlessly with other Microsoft products, such as Outlook and SharePoint, to create a unified communication environment

TASK: You are assigned to investigate this situation. Use SPLUNK to answer the questions below regarding the Conti ransomware. 

# start the Meachine

<p align="center">
<b>Root User</b>
<br/>
  <img src="START_Meachine.png"/>
<br/>
<br/>
</p>

Question 1: Can you identify the location of the ransomware?

<p align="center">
<b>Root User</b>
<br/>
  <img src="q_1.png"/>
<br/>
<br/>
</p>

Question 2: What is the Sysmon event ID for the related file creation event?

Sysmon Event ID 11: This event is logged by Sysmon (System Monitor) when a file is created or overwritten. It's useful for monitoring critical locations like the Startup folder, temporary directories, and download directories, which are common targets for malware

Question 3: Can you find the MD5 hash of the ransomware?

<p align="center">
<b>Root User</b>
<br/>
  <img src="q_3.png"/>
<br/>
<br/>
</p>

Question 4: What file was saved to multiple folder locations?

<p align="center">
<b>Root User</b>
<br/>
  <img src="q_4.png"/>
<br/>
<br/>
</p>


<p align="center">
<b>Root User</b>
<br/>
  <img src="q_4.1.png"/>
<br/>
<br/>
</p>


Question 5: What was the command the attacker used to add a new user to the compromised system?

<p align="center">
<b>Root User</b>
<br/>
  <img src="q_5.png"/>
<br/>
<br/>
</p>

<p align="center">
<b>Root User</b>
<br/>
  <img src="q_5.1.png"/>
<br/>
<br/>
</p>

<p align="center">
<b>Root User</b>
<br/>
  <img src="q_5.2.png"/>
<br/>
<br/>
</p>


<p align="center">
<b>Root User</b>
<br/>
  <img src="q_5final.png"/>
<br/>
<br/>
</p>

Question 6: The attacker migrated the process for better persistence. What is the migrated process image (executable), and what is the original process image (executable) when the attacker got on the system?

<p align="center">
<b>Root User</b>
<br/>
  <img src="q_6.png"/>
<br/>
<br/>
</p>

<p align="center">
<b>Root User</b>
<br/>
  <img src="q_6.2.png"/>
<br/>
<br/>
</p>

<p align="center">
<b>Root User</b>
<br/>
  <img src="q_6final.png"/>
<br/>
<br/>
</p>

Question 7: The attacker also retrieved the system hashes. What is the process image used for getting the system hashes?

<p align="center">
<b>Root User</b>
<br/>
  <img src="q_7.png"/>
<br/>
<br/>
</p>

Question 8: What is the web shell the exploit deployed to the system?
hint: IIS logs for post requests
Internet Information Services (IIS) it host websites ,application using microsoft technology including (aspx_file)

<p align="center">
<b>Root User</b>
<br/>
  <img src="q_8.png"/>
<br/>
<br/>
</p>

Question 9: What is the command line that executed this web shell?
attrib.exe  -r \\\\win-aoqkg2as2q7.bellybear.local\C$\Program Files\Microsoft\Exchange Server\V15\FrontEnd\HttpProxy\owa\auth\i3gfPctK1c2x.aspx

<p align="center">
<b>Root User</b>
<br/>
  <img src="q_9.png"/>
<br/>
<br/>
</p>

Question 10: What three CVEs did this exploit leverage?

CVE-2020-0796,CVE-2018-13374,CVE-2018-13379

<p align="center">
<b>Root User</b>
<br/>
  <img src="q_10.png"/>
<br/>
<br/>
</p>







