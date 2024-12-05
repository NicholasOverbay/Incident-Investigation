# Incident-Investigation NIST 800-61





Microsoft Sentinel Incident Investigation in accordance with NIST 800-61





![image](https://github.com/user-attachments/assets/da191f8e-c570-4c6b-8637-68192fdde436)





STEP 1, Preparation: Below are Custom Alert Rules I configured into Microsoft Sentinel Analytics. As the Logs Analytics Workspace begins to ingests logs, alerts will be triggered in response to suspicious activities and potential threats.





![image](https://github.com/user-attachments/assets/0d7d0308-8a40-427e-90ab-d0df77db1108)





STEP 2: Detection and Analysis; Upon observation, in Microsoft Azure Sentinel, I was alerted to an incident that I needed to investigate. Below, you can see incident number 47, with a High Severity rating titled, Custom: Brute Force Success.





![image](https://github.com/user-attachments/assets/714a3b30-bf08-43cd-b6d6-a603f3e0bfc3)





STEP 2: Detection and Analysis: Set Severity, Status, and Owner; Upon clicking on the incident, a details window opened on the right. This is where I will assign the event, updated the status, and set the severity.





![image](https://github.com/user-attachments/assets/e10ae98b-bc39-449f-849e-63c4b380b810)





STEP 2: Detection and Analysis: Set Severity, Status, and Owner; Here we can see that I assigned the event to myself, updated the status to active, and set the severity to high. Other important information revealed in the details window is there were two alerts, two events, the time, the date, and the entities involved, the destination host device, and the attackers Ip address.





![image](https://github.com/user-attachments/assets/0f2265de-d0cd-4364-9681-af64af0089dc)





STEP 2: Detection and Analysis: View Full Details; At the bottom of the details window, there is a View Full Details Tab. After clicking the View Full Details tab a new window appears.






![image](https://github.com/user-attachments/assets/8a6872be-19bd-4daa-b9a9-2c5054014173)




STEP 2: Detection and Analysis: View Full Details; Here in the View Full Details window, there is more information available. If you click on the attackers Ip address that is in blue under Entities, another window will open on the right and give location information.




![image](https://github.com/user-attachments/assets/30a20de4-a115-4d89-965a-c6345623e3dd)





STEP 2: Detection and Analysis: View Full Details; On the right-hand side you can view the location information from the attackers Ip address. The screenshot shows the ISP (internet service provider) is AT&T located in Cocoa Florida in the United States. On the bottom left there is a tab labeled investigate. After pressing the investigate tab a new window will appear.





![image](https://github.com/user-attachments/assets/627b6b48-ce8d-4124-8f30-bf90991aa2f7)





STEP 2: Detection and Analysis: Investigate Timeline; When clicking on the Investigate tab a new window opens and shows the Entity Mapping on the left, and the Timeline on the right. The Entity mapping will give you information about all entities involved in the incident and the Timeline will show the sequence of events in their order by time.




![image](https://github.com/user-attachments/assets/6728731e-299e-4b15-9b3c-d71d4df90330)




STEP 2: Detection and Analysis: Investigate entities; Below the Timeline tab there is an Entities tab. After clicking the Entities tab the window that opens will reveal the entities involved and the alerts. The entities involved in this incident are the Windows-VM and the attacker. Here is where you would see if any other entities or devices were involved in this incident.




![image](https://github.com/user-attachments/assets/81e20a9c-d999-4aec-9173-41b507262995)




STEP 2: Detection and Analysis: Investigate Entities; Here is an unsuccessful brute force attack in blue that contained 63 entities. These entities are other unsuccessful brute force attacks. If you click on the unsuccessful brute force attack, a window containing access to the 63 entities will appear on the right. When you click on view all 63 entities, where 63 entities is in blue, you will be taken to the logs screen.





![image](https://github.com/user-attachments/assets/d4bdc458-f581-4b13-bd4f-458f0fbdc921)




STEP 2: Detection and Analysis: Investigate Entities and Activity Logs; This is the Logs Analytics Workspace. Here in the logs, you can see all the log activities of the attacker. The query function is Get Host Related Alerts stated in the first line of the query. The query will summarize the security alerts, expand the entities, and filter for the alerts to the specified host. The host in this incident is the Windows Virtual Machine that was under the brute force attacks. At the bottom of the image on the right you will see a total of 71 brute force attacks that the query provided where the attacker tried to gain access. In the query below the very top log is the successful brute force attack.





![image](https://github.com/user-attachments/assets/b83177e3-ec0a-4b83-8429-a6f5670d8343)





STEP 2: Detection and Analysis: Investigate Entities; If you click on the very top log, the successful brute force attack, the log has a drop-down tap. Here in this log drop-down, there will be more information about the successful brute force logon. Now we will go back to the Entities Mapping Window.





![image](https://github.com/user-attachments/assets/168bafe1-1012-4989-9313-6da16236233f)





STEP 2: Detection and Analysis: Inspect Entities Involved; Here you can see the attacker in blue, the attackers Ip address, the host machine that was attacked in white, the successful brute force attacks in red circles, and the unsuccessful brute force attempts in yellow dotted circles.





![image](https://github.com/user-attachments/assets/e06c385c-aa60-43f3-abda-d854916c0140)





STEP 2: Detection and Analysis: Inspect Entities Involved and Related Events: When the attacker is clicked on, there is an event summary that comes up. If you click on more, it will give you an activity summary of what the attacker did while in the network or on the device. Activities such as installations, downloads, screenshots taken, any communications, data exchanges, parallel movements, bookmarks, etc. No other activities were detected.





![image](https://github.com/user-attachments/assets/869969c6-9382-4e54-981c-8811012fd2d1)





STEP 2: Detection and Analysis: Inspect Entities Involved and Legitimacy; The two successful brute force attacks are in blue. If you click on the successful attacks, information about the attacks will show up on the right-hand side. The information in the window on the right-hand side reveals that these are two separate logons at two separate times. This is a legitimate incident where an attacker has logged on and gained access to the same device two separate times.




![image](https://github.com/user-attachments/assets/0318839b-879d-4af3-a093-044526dc301d)
![image](https://github.com/user-attachments/assets/1373c822-8b27-4dc8-8aff-cb701fc7636e)




This is a true positive Brute Force Attack. Businesses would have a standard procedure that would need to be executed. There is usually a playbook that would need to be implemented, and the necessary communications would need to be made to inform the appropriate employees within the business to move forward. At this point in the NIST 800-61 Incident Management Lifecycle we would be entering STEP 3.STEP 3: Containment, Eradication, and Recovery.	The goal of containment is to limit the damage and prevent further spread of the incident. There are two types of containment strategies: Short-term containment: This involves immediate actions to stop the incident from causing more harm. Examples include isolating affected systems, blocking malicious IP addresses, and disabling compromised accounts. There is also Long-term containment: This involves more comprehensive measures to ensure the incident is fully contained. Examples include applying patches, reconfiguring firewalls, and implementing additional security controls.	Once the incident is contained, Eradication is next which eliminates the root cause of the incident. This may involve removing malware or malicious code from affected systems, identifying and closing vulnerabilities that were exploited, conducting a thorough investigation to ensure all traces of the incident are eradicated or out of the system.	After eradication, the focus shifts to recovery and restoring affected systems and services to normal operation. This includes restoring data from backups, rebuilding or reimaging compromised systems, monitoring systems closely to ensure they are functioning correctly and that the incident does not recur.STEP 4: Post-Incident Response:	 It’s important to conduct a post-incident review to learn from the incident and improve future response efforts. This involves documenting the incident and response actions, identifying lessons learned and areas for improvement, and updating incident response plans as well as procedures based on findings. By following these steps, you can effectively manage and recover from security incidents, minimizing their impact on your organization.

