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

## Part 1: Diagram
I used draw.io to make a diagram to logically map out the lab. 
<img width="2257" height="859" alt="Screenshot (46)" src="https://github.com/user-attachments/assets/049be0ce-a309-4ccc-a52e-498a2bd7112c" />

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




