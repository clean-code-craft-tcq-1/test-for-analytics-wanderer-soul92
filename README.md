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
5. Automation script for weekly report & mail notification 
6. Libraries to do testing of the software functionalities like Unitest 


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
3. Write "No record found" to the PDF when the csv is not avialable in the specified location/server
3. Write count of Breaches to the PDF from csv containing the telementry data when crosses the defined threshold
4. Write "No record Breach" to the PDF from csv when all records found within threshold
5. Write "No Positive Record" to the PDF when csv containing no postive value 
6. Write "No Negative Record" to the PDF when csv containing no postive value 
7. 



(add more)

### Recognize Fakes and Reality

Consider the tests for each functionality below.
In those tests, identify inputs and outputs.
Enter one part that's real and another part that's faked/mocked.

| Functionality            | Input        | Output                      | Faked/mocked part
|--------------------------|--------------|-----------------------------|---
Read input from server     | csv file     | internal data-structure     | Fake the server store
Validate input             | csv data     | valid / invalid             | None - it's a pure function
Notify report availability | _enter input | _enter output               | _enter fake or mock
Report inaccessible server | _enter input | _enter output               | _enter fake or mock
Find minimum and maximum   | _enter input | _enter output               | _enter fake or mock
Detect trend               | _enter input | _enter output               | _enter fake or mock
Write to PDF               | _enter input | _enter output               | _enter fake or mock
