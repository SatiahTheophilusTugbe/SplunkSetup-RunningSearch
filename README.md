# SPLUNK SETUP - DATA INJESTION - RUNNING SEARCH
# Project Overview
This detailed guide will walk you thru on how to effectively utilize Splunk for log analysis and continuous monitoring. This step by step guide is based on my recent hands-on experience with Splunk. 
This repository will walk you through the essential steps for setting up Splunk, uploading logs, performing queries, and leveraging Splunk's capabilities to enhance your cybersecurity posture.

- Table of Contents
- Introduction
- Setting Up Splunk
- Uploading Logs
- Performing Queries
- Analyzing Results
- Conclusion

# Introduction
Splunk is a widely-used platform for searching, monitoring, and analyzing machine-generated big data through a web-style interface. In this guide, I’ll take you through the steps of using Splunk
for continuous monitoring, focusing on log uploads, query execution, and basic analysis. These tasks are critical for real-time incident detection and forensic investigation.

# Setting Up Splunk
- To begin, we need to set up Splunk on your system. This involves downloading and installing Splunk:
- Visit Splunk’s official website and download the latest version suitable for your operating system.
- Follow the installation guide provided on the website to install Splunk. 

# For Ubuntu users, 
- run: sudo dpkg -i splunk-package-name.deb
- Start the Splunk service using: sudo /opt/splunk/bin/splunk start
- Complete the setup by setting up an admin username and password.

- From my lab Ubuntu box, I’ve set up a Guacamole box for remote access, making it easier to manage our Splunk environment.

![1](https://github.com/user-attachments/assets/da07a183-9f06-414f-9a0c-d558c222c210)

# Access Splunk Web Interface:

- Open your web browser and navigate to:
- http://localhost:8000
- Log in using the admin credentials you created during installation.

![2](https://github.com/user-attachments/assets/39cb13be-9e9d-44cd-be4f-2adfc5e3db70)

- Once Logged into Splunk Web Interface:

![3](https://github.com/user-attachments/assets/26b55cc2-0efd-46f0-b9c1-2636ecfb2412)

# Uploading Logs

After setting up Splunk, the next step is to upload your logs for analysis:

Navigate to the Data Inputs Section:
- In the Splunk web interface, go to the "Settings" dropdown and select "Data Inputs."
- Choose the type of data source (e.g., file, directory) you want to upload.
- Upload the Logs
  
![4](https://github.com/user-attachments/assets/1622365f-48d4-460c-9a4c-d68383bffdd5)

- Specify the path to your log files. For example, if your logs are stored in /var/log/syslog, you would enter this path.
- Follow the prompts to index your data. You can choose to categorize the logs under a specific index name for easier access later.
- Verify the Upload:

![5](https://github.com/user-attachments/assets/3eeefc2d-6ba4-46bf-965d-aa0a5506ccb2)

- Once uploaded, navigate to the "Search & Reporting" app in Splunk.
- Type the following query to see the first few records from your logs:
- Type: source="*" host=LinuxDemo (your_index_name) | head 20

![15](https://github.com/user-attachments/assets/c8f2c2af-1030-497f-8267-f3c0c0f875ac)

# Performing Queries
Querying is a powerful feature of Splunk that allows you to sift through vast amounts of data quickly:

Basic Query:
- Start with a simple query to search for a specific IP Address from a specific log already injested by the tool.
- For Example: Searching for Source IP: 10.11.36.17

![6](https://github.com/user-attachments/assets/fc32e55f-3159-4406-831a-dbc9e0af4d5d)

- For Example: Searching for Destination IP: 10.11.36.17

![9](https://github.com/user-attachments/assets/1d6c180d-5470-49ab-b38a-2ee46c699af0)

- Performing a simple query for a specific operating system.
- For Example: Searching for Windows OS from a specific log.

![7](https://github.com/user-attachments/assets/5586b34e-3d62-45f9-b304-918a9980e0f8)

- For Example: Running a search for Linux OS from a specific log.
  
![8](https://github.com/user-attachments/assets/ec0d865b-4f9b-490a-b059-b34e0750e287)

- For Example: Running a search for Citrix Zscaler OS from a specific log.

![11](https://github.com/user-attachments/assets/6aba09d4-97ee-4a5c-b627-0b7557e1acb0)

- Performing a simple query for a specific terms, signature, interests and events.
- For Example: Searching for a specific signature such as Win RDP Server MITM Weakness.
  
![10](https://github.com/user-attachments/assets/c0685f20-2587-48fb-b69c-9eb5229ae25a)

- For Example: Searching for a specific event such as " A user account was locked out".

![12](https://github.com/user-attachments/assets/426110c4-2599-4b29-8ba6-fed88cdccc99)

- For Example: Searching for a specific event such as " A user account was deleted".

![13](https://github.com/user-attachments/assets/bab44cfa-fbe2-4a8e-acba-ab0972359940)

- For Example: Searching for a specific event such as " Eventcode 4738".

![14](https://github.com/user-attachments/assets/4be54772-73dc-4e00-9712-19aecb28cf46)

# Filtering and Sorting:

- You can filter logs based on specific conditions, such as error messages or specific IP addresses:
- For example: Sorting an IP address:

![17](https://github.com/user-attachments/assets/ad132282-bda7-4b11-aa29-84e5f689092f)

# Additional Splunk perimeters:
- Saving Queries:
Once you have a query that provides useful insights, save it for future use by clicking on the "Save As" option in the Splunk interface.
- Analyzing Results:
The analysis phase involves interpreting the data returned by your queries:
- Identify Patterns:
Look for recurring patterns in the logs that may indicate security incidents, such as repeated failed login attempts.
- Correlation Rules:
Set up correlation rules within Splunk to automatically flag suspicious activities, such as brute-force attacks

# Visualization:
Use Splunk's visualization tools to create dashboards that display real-time data trends, helping in the quick identification of anomalies.

# Conclusion
Using Splunk for log management and analysis significantly enhances your ability to detect and respond to security incidents. By following these steps, you will be well on your way to mastering Splunk and leveraging its full potential to protect your organization’s digital assets.

- Feel free to explore the code snippets, queries, and additional resources included in this repository to deepen your understanding of Splunk’s capabilities.
