# CVAT API Script

### Purpose
Making automatic transactions over csv in CVAT.

### Config File
includes:
•	[server]
    ◦	host= 
    ◦	port=
•	[log]
    ◦	log_file=True
•	[user]
    ◦	username=
    ◦	password=

* Server information is required to access CVAT.
* If log_file is True, logs will be saved to the file. If false, it will not be saved to the file.
* Username and password are required to log in. This section will be blank at first. If this part is empty, these will be requested on the console.


### Csv File Format
In the first line of the file, these headings should be “Organization, Project, TaskName, UploadType, UploadPath, Assignee, JobStage, JobState”. The entered information should not be wrong, this information is checked with the check() command.

### Script Commands
There are 6 main commands in total. These are as follows:
<h2>1.	Check</h2>
```python3 cvat_script.py check_csv <csv_file>``` </br>
for example: ```python3 cvat_script.py check_csv csv_file.csv```

<h3>Purpose</h3>: It checks whether the contents of the csv_file file whose path is given are in the appropriate format. If the format is correct, the message format True is returned. If false, it lists where the errors are.
<h2>How It Works</h2>: If there is missing information in the given csv file, it gives the warning "{index}. row is empty or wrong", this is not an error. Checks whether the information in the Organization, Project, TaskName, Assigne columns is in CVAT. If there is no information available, it will throw an error.
