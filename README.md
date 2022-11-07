# Honeypot Assignment

**Time spent:** 4 hours spent in total

**Objective:** Create a honeynet using MHN-Admin. Present your findings as if you were requested to give a brief report of the current state of Internet security. Assume that your audience is a current employer who is questioning why the company should allocate anymore resources to the IT security team.

### MHN-Admin Deployment (Required)

**Summary:** How did you deploy it? Did you use GCP, AWS, Azure, Vagrant, VirtualBox, etc.?

I deployed the MHN server through GCP. I created the necessary virtual machines through the CLI but it was hosted on the free trial of GCP (Google Cloud Platform) I also utilized virtual box to host my kali linux machine that was used to send attacks to the honeypot as a means to test if my honeypot was receiving data. 

GIF Walkthrough: ![](https://github.com/michaelbanegas/Codepath_Cybersecurity_HW/blob/Project-9-Honeypot/mhn%20admin.gif)

### Dionaea Honeypot Deployment (Required)

**Summary:** Briefly in your own words, what does dionaea do?

Dionaea is a type of honeypot that is used to trap and isoloate outsite attacks that are trying to exploit vulnerabilities/inject malware into servers. With honeypots, cybersecurity personal can then extract samples found online in their honeypots and dissect them to learn more about the ever changing world of malware as well as improve their own protection. 

GIF Walkthrough: ![](https://github.com/michaelbanegas/Codepath_Cybersecurity_HW/blob/Project-9-Honeypot/honeypot.gif)

### Database Backup (Required) 

**Summary:** What is the RDBMS that MHN-Admin uses? What information does the exported JSON file record?

MHN-Admin uses the MongoDB RDBMS. The information that is exported in the JSON file record would be all the instances of attacks that were captured by our honeypot. 

GIF Walkthrough: ![](https://github.com/michaelbanegas/Codepath_Cybersecurity_HW/blob/Project-9-Honeypot/json.gif)

JSON File: ![](https://github.com/michaelbanegas/Codepath_Cybersecurity_HW/blob/Project-9-Honeypot/session.json)

*Be sure to upload session.json directly to this GitHub repo/branch in order to get full credit.*

## Notes

Describe any challenges encountered while doing the assignment.
