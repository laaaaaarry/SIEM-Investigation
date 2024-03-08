# SIEM-Investigation

## Objective

The SIEM Investigation project sought to deepen the understanding of Sentinel SIEM's investigative and informative capabilities as well as aiming to optimize its functionalities for comprehensive incident analysis and response.

## Skills Learned

- Proficiency in log analysis and correlation for identifying suspicious activities.
- Enhanced skills in real-time event monitoring and threat detection.
- Capability to conduct forensic investigations using Sentinel's comprehensive data collection.
- Expertise in creating and fine-tuning alerts for proactive threat identification.
- Mastery in proactive threat hunting through Sentinel SIEM's advanced search and query capabilities.
- Enhanced skills in leveraging threat intelligence feeds to enrich and contextualize security data.

## Tools Used

- Azure Sentinel (SIEM) for investigating & threat hunting

## Steps

1. Open Azure portal navigate to Sentinel workspace & go to **Incident** view of the Sentinel workspace.
2. From the list select "Solorigate Network Beacon" incident.

![image](https://github.com/laaaaaarry/SIEM-Investigation/assets/125237930/2c9c604a-3e71-4614-9b5e-37c8a9323e51)

3. Assign the incident to yourself & click Apply.

![1](https://github.com/laaaaaarry/SIEM-Investigation/assets/125237930/0548af6b-18d9-4a3e-81cf-6cac9e448fe5)

4. Read the description of the incident. As you can see, one of the domain IOCs related to Solorigate attack has been found. In this case, domain avsvmcloud.com is involved.
5. Optionally, you can click on View full details to drill down to inspect the raw events that triggered this alert. For that, click an Alert in the timeline, and click on Link to LA.
6. As you can see, the events originated in Cisco Umbrella DNS, and the analytic rule uses Advanced Security Information Model (ASIM) to normalize these events from any DNS source.
7. Next we will try to identify hosts which might have been compromised. Click on Hunting tab on Sentinel Menu & select Queries tab if not selected.
8. In the search box, type "solorigate". Select the Solorigate Inventory check query and click on Run Query.
9. You should see a total of three results. Click on View Results
10. As you can see, besides ClientPC, there are two additional computers where the malicious DLL and named pipe have been found. Bookmark all three records, by selecting them with the tickboxes on the left, and clicking on Add bookmark.
11. In the Add bookmarks window that appears, click on Create to create the bookmarks. As you can see entity mapping is already done for you.
12. Now close log search you will be in Bookmark tab where we can see 2 new bookmarks created. Select both & click add on incident actions at top & add to existing incident.
13. From the list, pick the Solorigate incident that is assigned to you, and click Add.
14. Now, we will add the IP address related to the incident to our list of Indicators of Compromise (IOC) in our Sentinel workspace Threat Intelligence store, so we can capture any new occurrences of this IOC across our logs.
15. Go back to the Incidents view. Select the Solorigate incident and copy the IP address involved. Notice that you now have more computer entities available for selection, as they were added to the incident from the bookmarks' entities.
16. Go to the Threat Intelligence blade in Microsoft Sentinel and click Add new at the top.
17. Enter the following details in the New indicator dialog, with Valid from being today's date and Valid until being two months after. Then click Apply.
18. We will now prepare the incident for handover to another team (maybe Operations or Forensics) by ensuring what we've done is documented.
19. Go to Incidents & select the Solorigate incident assigned to you. Click on View full details. Move to Comments tab.
20. Enter information about all the steps performed.





## Documentation

* IOC detected, avsvmcloud.com domain is detected which is indicator of Solorigate attack.
* 
