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

JSON File: Was uploaded to the repository/branch of this assignment: URL --> https://github.com/michaelbanegas/Codepath_Cybersecurity_HW/blob/Project-9-Honeypot/session.json

*Be sure to upload session.json directly to this GitHub repo/branch in order to get full credit.*

## Notes

After setting up both VMs and creating a honeyput within MHN-Admin, I was not getting any attacks in my honeypot. After some troubleshooting, there was a resource posted in the class' slack help channel that ended up solving my issue. It was discovered that I needed to note out 5 lines of code in a file within the ssh MHN-Admin repositories and reset the programs. After this was completed I then needed to rerun the wget command given in MHN within my honeypot vm. Soon after my honeypot was getting attack and I was able to get data for this assignment. 

Steps Followed to fix:

1. n cmd open your ssh mhn-admin
2. Run 'sudo supervisorctl status'
3. Verify that mnemosyne isn't working
4. Run " sudo apt-get install nano' (Unless you already have it)
5. You're going to then run 'cd /opt/mnemosyne/env/lib/python2.7/site-packages/gevent  (This is a directory)
6. In the directory run 'sudo nano hub.py'
7. Things are gonna get a little more involved 
8. Comment out by using # the 5  lines in red from the picture
9. Exit and press Enter followed by running 'cd'
10. Run 'sudo supervisorctl restart all'
11. Once completed run the first script from the start to verify everything is working
12. Once again run the script you obtain from mhn server browser, should start with 'wget'
13. Go to your VM in kali or docker and do the attack again and now there should be attacks
