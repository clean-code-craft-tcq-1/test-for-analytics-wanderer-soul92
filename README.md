# Test for Analytics

Design tests for Analytics functionality on a Battery Monitoring System.

Fill the parts marked '_enter' in the **Tasks** section below.

## Analysis-functionality to be tested

This section lists the Analysis for which _tests_ must be written.

Battery Telemetrics are collected and stored on a server.
Data for a month is stored in a [csv file](https://en.wikipedia.org/wiki/Comma-separated_values).

Analysis must be done on this csv file to find the following:
- minimum
- maximum
- count of breaches (how many times did it cross the threshold in a month?)
- record trends (date & time when the reading was continuously increasing for 30 minutes)

A PDF report of the analysis must be stored every week.
Notification must be sent when a new report is available.

## Tasks

### List Dependencies

List the dependencies of the Analysis-functionality.

1. Access to the Server containing the telemetrics in a csv file
2. Libraries like Pandas, Numpy to read CSV and mathematical operations 
3. Libraries to identify/detect  for increasing trends and record 
4. Libraries to convert captured data to PDF 
5. Autherizatiob credentials and admin access to for server autherization/APIs access
5. Automation script/server side libs for weekly report & mail notification 
6. Libraries to do testing of the software functionalities like Unitest
7. defined thresholds and arguments 


### Mark the System Boundary

What is included in the software unit-test? What is not? Fill this table.

| Item                      | Included?     | Reasoning / Assumption
|---------------------------|---------------|---
Battery Data-accuracy       | No            | We do not test the accuracy of data
Computation of maximum      | Yes           | This is part of the software being developed
Computation of minimum      | Yes           | This is part of the software being developed
Off-the-shelf PDF converter | Yes 			| PDF is among the deliverables of the software being developed 
Counting the breaches       | Yes			| This is part of the software being developed and to be captured in records 
Detecting trends            | Yes			| Trend detection is recorded in PDF for weekly notification 
Notification utility        | Yes 			| Weekly mail notification of the pdf 

### List the Test Cases

Write tests in the form of `<expected output or action>` from `<input>` / when `<event>`

Add to these tests:

1. Write minimum and maximum to the PDF from a csv containing positive and negative readings
2. Write "Invalid input" to the PDF when the csv doesn't contain expected data
3. Write #Zero Record found" to the PDF when the csv is not avialable in the specified location/server
4. Write "Server Connection not established" when server is out of reach 
5. Write "Wrong File Extention" when Excel is not in specified CSV format
6. Write "Validation Succesfull" when CSV file is having right data in at correct Header/Columns
7. Write "Invaid data" when CSV file is having data in wrong format
8. Write count of Breaches to the PDF from csv containing the telementry data when crosses the defined threshold
9. Write "No breach" to the PDF from csv when all records found within threshold
10. Write "Zero Positive Record" to the PDF when csv containing no postive value 
11. Write "Zero Negative Record" to the PDF when csv containing no postive value 
12. Write timestemp details from csv to PDF when contineous increasing reading found for 30 min 
13. Write "Zero Record" when no contieous reading found for 30 min 
14. Write "successfull saved" when PDF is genrated and saved in mentioned path/location/server
15. Write "invalid receipient" when unvalid emaild is found while sending notifcation
16. Write "Email delivered" when email delivery is succesfull 
17. Write "Error Msg" when notification is unsuccesfull 
	

(add more)

### Recognize Fakes and Reality

Consider the tests for each functionality below.
In those tests, identify inputs and outputs.
Enter one part that's real and another part that's faked/mocked.

| Functionality            | Input        | Output                      | Faked/mocked part
|--------------------------|--------------|-----------------------------|---
Read input from server     | csv file     | internal data-structure     | Fake the server store
Validate input             | csv data     | valid / invalid             | None - it's a pure function
Notify report availability | PDF		  | mail notification           | Fake notify module
Report inaccessible server | server path  | message/ error code         | Fake the server access 
Find minimum and maximum   | csv file	  | min and max values          | None - it's a pure function
Detect trend               | csv file     | date and time               | None - it's a pure function
Write to PDF               |function data | PDF entry                   | Fake 
