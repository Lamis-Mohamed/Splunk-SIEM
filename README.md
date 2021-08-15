# Splunk-SIEM


The dataset is based on different web logs from linux server and Cisco WSA so before you start working on the task make sure you have Splunk Add-on for Unix and Linux and Splunk Add-on for Cisco WSA 

 

Task 1: Chart the total daily volume (in MB) of the web servers based on ea ch week. 

Search online purchases [access_combined] and answer with the query you have  used. 

Use timechart to calculate the total bytes and name the field: bytes 

Use eval to convert the bytes field to megabytes. 

Hint: megabytes=bytes/(1024*1024) 

Use the round function to round the megabytes field values to two decimal places. 

Switch to the Visualization tab and display the data as a Line Chart. Set the X-axis label to Day. Notice that the bytes field still displays. 

Use the fields command to remove the bytes field. 

Note after every step screenshot the results you get. 

 

Task 2: Identify users with more than 3 failed logins on 15th Dec 2017 and sort in descending order. Or since our dataset is from December 2017 just display the highest failed login ins on 15th December 2017. And well sorted out in descending order. 

 

 

Task 3: Report common HTTP status errors that occurred during that month in 2017 on the online sales web servers and the internal web appliance within a proximity of 5 minutes or less. Only include days with more than 5 common errors. 

 Search HTTP status error events from the online sales web servers [access_combined] and the web appliance [cisco_wsa_squid] during the last 30 days. For best performance, limit extracted fields to only sourcetype and status. 

Hint: 

network sourcetype=cisco_wsa_squid) OR  

(index=web sourcetype=access_combined) status>399| fields sourcetype, status 

 Create transactions based on status field values and limit the span to 5 minutes. 

 Limit the results to only transactions that contain at least one event from each sourcetype. 

 Use timechart to count events by status.  

 Discard rows that have fewer than 5 errors for all status values. 

Hint: Use addtotals. 

| addtotals  

 You will have a Total column, Remove the Total column and display the data as a Line chart and screen shot your work process. 
