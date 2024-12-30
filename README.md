# Lets-go-Splunking

Step 1: The Need for Speed

Background: As the worldwide leader of importing and exporting, Vandalay Industries has been the target of many adversaries attempting to disrupt their online business. Recently, Vandaly has been experiencing DDOS attacks against their web servers. Not only were web servers taken offline by a DDOS attack, but upload and download speed were also significantly impacted after the outage. Your networking team provided results of a network speed run around the time of the latest DDOS attack. Task: Create a report to determine the impact that the DDOS attack had on download and upload speed. Additionally, create an additional field to calculate the ratio of the upload speed to the download speed.

I uploaded a file named **Speed_test** containing system speed data recorded around the time of the attack.

The table created from the **Speed_test** file is shown below:

![image](https://github.com/user-attachments/assets/d96a90dd-a1a0-484d-a8b2-e4ff8b06cd35)
![image](https://github.com/user-attachments/assets/925bcc6f-b9a8-4caf-83de-4cdcee26a99c)
![image](https://github.com/user-attachments/assets/7d735d01-7fe7-4333-9df3-da9052ffe984)

Based on the report created, what is the approximate date and time of the attack?

In the above report, the attack occurred at 14:30 on February 23, 2020. after that the Systems recovered and was operating normally by 23:00 on February 23, 2020, representing a total recovery time of 8 hours and 30 minutes


Step 2: Are We Vulnerable?

Background: Due to the frequency of attacks, my manager needs to be sure that sensitive customer data on their servers is not vulnerable. Since Vandalay uses Nessus vulnerability scanners, I have pulled the last 24 hours of scans to see if there are any critical vulnerabilities.

For more information on Nessus, read the following link: https://www.tenable.com/products/nessus

I Create a report that determining how many critical vulnerabilities exist on the customer data server. The database server IP is 10.11.36.23, and The field that identifies the level of vulnerabilities is severity.

The created report is shown below:

![image](https://github.com/user-attachments/assets/e9cdc4aa-a676-42ea-ada2-d57f2e41379d)
![image](https://github.com/user-attachments/assets/285a098b-1824-4cf9-ba27-59a1eca6b7fd)

I created an alert that runs daily to check for any critical vulnerabilities on the server. If a vulnerability is detected, an alert is sent via email to **soc@vandalay.com**.

Proof the alert has been created:
![image](https://github.com/user-attachments/assets/f4058d2b-71d8-4ee3-a8e2-d20c2a1886be)



Step 3: Drawing the (Base)line

Background: A Vandaly server is also experiencing brute force attacks into their administrator account. Management would like you to set up monitoring to notify the SOC team if a brute force attack occurs again.

Your Task: Analyze administrator logs that document a brute force attack. Then, create a baseline of the ordinary amount of administrator bad logins and determine a threshold to indicate if a brute force attack is occurring. 


When did the brute force attack occur?

The attack occurred between 9:00 AM and 1:00 PM on February 21, 2020.

![image](https://github.com/user-attachments/assets/d2a4e8d3-dc50-4133-b342-01cf8dd52a39)




Determine a baseline of normal activity and a threshold that would alert if a brute force attack is occurring:

Normal failed login activity typically varies between 6 and around 20 attempts per hour. However, during the hours of the attack, the failed login attempts surged to 124, 101, 121, 95, and 123. Establishing a baseline for regular failed login activity could be set at 25 failed attempts per hour, with an alert triggered when the attempts exceed 50 per hour.

I created an alert to check the threshold every hour and email the SOC team at SOC@vandalay.com if triggered.

![image](https://github.com/user-attachments/assets/5722de2d-c446-4f07-b46f-46219f9c2148)










