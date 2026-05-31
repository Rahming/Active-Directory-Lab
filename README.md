# Active-Directory-Lab

## Objective
Create a active directory envoirnment and integrate Splunk, Slack and Shuffle to automate responsive actions.

### Skills Learned
- 
- 
- 
- 
- 

### Tools Used

- VMware Workstation
- Splunk
- Slack
- Shuffle
- Draw.io
### MITRE ATT&CK Techniques
-
-
## Part 1: Diagram
I used draw.io to make a diagram to logically map out the lab. 
<img width="2249" height="857" alt="Untitled" src="https://github.com/user-attachments/assets/d58f4c89-0911-46bc-965c-f9b2edffbda5" />


#### As shown in the screen shot:
1. The attacker machine will perform a sucessful authenication on the test machine 
2. The test machine will send a telemerty to the Ubuntu machine(Splunk)
3. The ubuntu machine(Splunk) will generate an alert to slack and also send a web hook to shuffle to trigger the playbook
4. Shuffle will send a email notification to SOC analyst to disable user 
5. If no, nothing happens
6. If yes, shuffle will instruct the Domain Controller machine to disable the domain user
7. Once the Domain controller machine disables the user, Shuffle will send a notification to slack stating "the user has been disabled"

## Part 2: Installing Virtual Machines
I will use VMware workstation to create 3 virtual machines. Ubuntu 22.04 (splunk) and 2 Windows server 2022(Domain controller and Test machine).

I had a issue when setting up windows server 2022 the screen would get stuck here:
<img width="2556" height="1223" alt="Screenshot (54)" src="https://github.com/user-attachments/assets/1d29e770-d26b-4bd5-ac16-9a7653975f3e" />

going into the virtual machine settings and change to use floppy image file fixes the issue
<img width="2120" height="1218" alt="Screenshot (55)" src="https://github.com/user-attachments/assets/4b418f8a-45a2-4037-ac28-fe92728a9d7e" />

There are inbound rules that need to be enabled so the virtual machines can communicate 

<img width="1924" height="1202" alt="Screenshot (59)" src="https://github.com/user-attachments/assets/eb39c642-c3bd-41be-b908-7ccfcc421879" />
<img width="1913" height="1171" alt="Screenshot (65)" src="https://github.com/user-attachments/assets/c006d20a-5da3-49f9-8110-72db3026e45d" />

Now I made restrictive firewall rules to practice good security

for windows virtual machines
<img width="1925" height="1200" alt="Screenshot (60)" src="https://github.com/user-attachments/assets/dc7c0ea3-320f-4381-a562-486e60859852" />
<img width="1930" height="1206" alt="Screenshot (61)" src="https://github.com/user-attachments/assets/7b78a031-8ba1-49cb-b2b4-f5f6b6ea7d3c" />

For Ubuntu machine
<img width="1924" height="1205" alt="Screenshot (64)" src="https://github.com/user-attachments/assets/70926628-3100-4adf-bda2-81fedb538cc7" />
