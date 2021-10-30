### Step 1: The Need for Speed

Background: As the worldwide leader of importing and exporting, Vandalay Industries has been the target of many adversaries attempting to disrupt their online business. Recently, Vandaly has been experiencing DDOS attacks against their web servers.
Not only were web servers taken offline by a DDOS attack, but upload and download speed were also significantly impacted after the outage. Your networking team provided results of a network speed run around the time of the latest DDOS attack.
Task: Create a report to determine the impact that the DDOS attack had on download and upload speed. Additionally, create an additional field to calculate the ratio of the upload speed to the download speed.


I Upload the following file Called Speed_test in the system speeds around the time of the attack.


The Speed_test created table is shown below:
![speed test file](./Images/snap_1.png)

- Based on the report created, what is the approximate date and time of the attack?
    - In the above report, the attack occurred at 14:30 on February 23, 2020. after that the Systems recovered and was operating normally by 23:00 on February 23, 2020, representing a total recovery time of 8 hours and 30 minutes

### Step 2: Are We Vulnerable?

Background:  Due to the frequency of attacks, my manager needs to be sure that sensitive customer data on their servers is not vulnerable. Since Vandalay uses Nessus vulnerability scanners, I have pulled the last 24 hours of scans to see if there are any critical vulnerabilities.

For more information on Nessus, read the following link: https://www.tenable.com/products/nessus


I Create a report  that determining how many critical vulnerabilities exist on the customer data server. 
The database server IP is 10.11.36.23, and The field that identifies the level of vulnerabilities is severity.

The created report is shown below:
![created a report](./Images/snap_2.png)
![created a report](./Images/snap_2y.png)



I Build an alert that monitors every day to see if this server has any critical vulnerabilities. If a vulnerability exists, I have an alert emailed to soc@vandalay.com.

Proof the alert has been created:
![Alert](./Images/snap_y.png)
![Alert](./Images/snap_xy.png)


### Step 3: Drawing the (base)line

Background:  A Vandaly server is also experiencing brute force attacks into their administrator account. Management would like you to set up monitoring to notify the SOC team if a brute force attack occurs again.
Task: Analyze administrator logs that document a brute force attack. Then, create a baseline of the ordinary amount of administrator bad logins and determine a threshold to indicate if a brute force attack is occurring.

- When did the brute force attack occur?
    - The attack occurred between 9:00 AM and 1:00 PM on February 21, 2020.
    
    ![Alart brute force](./Images/snap-3.png)
    
    ![Alart brute force](./Images/snap-3y.png)

- Determine a baseline of normal activity and a threshold that would alert if a brute force attack is occurring.
    -  Normal activity with regard to failed login attempts seems to fluctuate between six (6) and approximately 20 attempts per hour. During each of the hours of the attack, the number of failed login attempts increased to 124, 101, 121, 95, and 123. A baseline of normal failed login attempt activity might be 25 failed attempts per hour, with a threshold of 50 attempts per hour triggering an alert.


I Design an alert to check the threshold every hour and email the SOC team at SOC@vandalay.com if triggered.

Proof the alert has been created:
![Alart brute force](./Images/snap-3x.png)
