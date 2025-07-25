🛡️ Log Enrichment Project

This repository contains system log data and enriched logs for further analysis and visualization. The goal of this project is to demonstrate how raw system logs can be transformed into enriched datasets for better insights into system activities and security events.

📂 Repository Structure

.
├── combined_logs.log      # Raw combined log file collected from multiple sources  
├── enriched_logs.csv      # Enriched log file with added contextual information  
└── README.md              # Project documentation  


📜 Description
🔹 combined_logs.log

This is a concatenated log file that includes entries from the following sources:

    /var/log/httpd/access_log

    /var/log/messages

    /var/log/secure

    /var/log/cron

    /var/log/custom_app.log

These logs were combined using the following command on an EC2 instance:

sudo sh -c 'tail -F /var/log/httpd/access_log /var/log/messages /var/log/secure /var/log/cron /var/log/custom_app.log >> /var/log/combined_logs.log'

🔹 enriched_logs.csv

This CSV file contains enriched data parsed from the original log file using a custom Python script. It includes the following fields:

    Timestamp

    Log Level

    Source / Service

    IP Address (if present)

    Message Content

    Category (e.g., authentication, HTTP access, cron jobs)

⚙️ Tools & Technologies Used

    Python 3

    Regular Expressions (re module)

    Linux Shell (e.g., tail, cat, sh)

    Amazon EC2

    GitHub

📊 Use Cases

    Log analysis for system performance

    Intrusion detection and system auditing

    Visualizing trends in server activity

    Feeding into SIEM tools or dashboards
