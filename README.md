<h1>Use regular expressions to find patterns</h1>

<h2>Introduction</h2>

Security analysts often analyze log files, including those that contain information about login attempts. For example as an analyst, you might flag IP addresses that relate to unusual attempts to log in to the system.

Another area of focus in cybersecurity is detecting devices that require updates. Software updates help prevent security issues due to vulnerabilities.

Using regular expressions in Python can help automate the processes involved in both of these areas of cybersecurity. Regular expression patterns and functions can be used to efficiently extract important information from strings and files.

In this lab, you'll write regular expressions to extract information such as device IDs or IP addresses.

<h2>Scenario</h2>

In this lab, you're working as a security analyst and your main tasks are as follows:

extracting device IDs containing certain characters from a log; these characters correspond with a certain operating system that requires an update.
extracting all IP addresses from a log and then comparing them to those that are flagged in a list.

<h3>Task 1</h3>

In order to work with regular expressions in Python, start by importing the re module. This module contains many functions that will help you work with regular expressions. By running the following code cell, the module will be available through the rest of the notebook.

<img src="https://i.imgur.com/ZZjOG2S.png" height="80%" width="80%"/>

<h3>Task 2</h3>

In your work as a cybersecurity analyst, you're responsible for updating devices. A device ID that begins with the characters "r15" indicates that the device has a certain operating system that must be updated.

You're given a log of device IDs, stored in a variable named devices. Your eventual goal is to extract the device IDs that start with the characters "r15". For now, display the contents of the whole string to examine what it contains. Be sure to replace the ### YOUR CODE HERE ### with your own code before you run the following cell.

<img src="https://i.imgur.com/aBnqmX0.png" height="80%" width="80%"/>

<h3>Task 3</h3>

In this task, you'll write a pattern to find devices that start with the character combination of "r15".

Use the regular expression symbols \w and + to create the pattern, and store it as a string in a variable named target_pattern.

Be sure to replace the ### YOUR CODE HERE ### with your own code before you run the following cell. Note that the code cell will contain only variable assignments, so running it will not produce an output.

<img src="https://i.imgur.com/rTzohnN.png" height="80%" width="80%"/>

<h3>Task 4</h3>

Use the findall() function from the re module to find the device IDs that the target_pattern matches with. Be sure to replace the ### YOUR CODE HERE ### with your own code before you run the following cell.

Note: In order to use re.findall() in Tasks 4, 7, 8, 9 and 11, you must have previously run the code import re in Task 1.

<img src="https://i.imgur.com/woLrCju.png" height="80%" width="80%"/>

<h3>Task 5</h3>

Now, the next task you're responsible for is analyzing a network security log file and determining which IP addresses have been flagged for unusual activity.

You're given the log file as a string stored in a variable named log_file. There are some invalid IP addresses in the log file due to issues in data collection. Your eventual goal is to use regular expressions to extract the valid IP addresses from the string.

Start by displaying the contents of the log_file to examine the details inside. Be sure to replace the ### YOUR CODE HERE ### with your own code before you run the following cell.

<img src="https://i.imgur.com/vYub9mx.png" height="80%" width="80%"/>

<h3>Task 6</h3>

In this task, you'll build a regular expression pattern that you can use later on to extract IP addresses that are in the form of xxx.xxx.xxx.xxx. In other words, you'll extract all IP addresses that contain four segments of three digits that are separated by periods.

Write a regular expression pattern that will match with these IP addresses and store it in a variable named pattern. Use the regular expression symbols \d and \. in your pattern. Note that the symbol \d matches with digits, in other words, any integer between 0 and 9. Be sure to replace the ### YOUR CODE HERE ### with your own code. Since you'll just build the pattern here, there won't be any output when you run this cell.

<img src="https://i.imgur.com/HGhETpl.png" height="80%" width="80%"/>

<h3>Task 7</h3>

In this task, you'll use the re.findall() function on the regular expression pattern stored in the pattern variable and the provided log_file to extract the corresponding IP addresses. Afterwards, run the cell and take note of what it outputs. Be sure to replace the ### YOUR CODE HERE ### with your own code before you run the following cell.

<img src="https://i.imgur.com/9XOd5O9.png" height="80%" width="80%"/>

<h3>Task 8</h3>

There are some valid IP addresses in the log_file that you haven't extracted yet. This is because each segment of digits in a valid IP address can have anywhere between one and three digits.

Adjust the regular expression in the pattern to allow for variation in the number of digits in each segment. You can do this by using the + symbol after the \d symbol. Afterwards, use the updated pattern to extract remaining IP addresses. Then, run the cell to analyze the results. Be sure to replace the ### YOUR CODE HERE ### with your own code before you run the following cell.

<img src="https://i.imgur.com/9Bgu4E4.png" height="80%" width="80%"/>

<h3>Task 9</h3>

Note that all the IP addresses are now extracted but they also include invalid IP addresses with more than three digits per segment.

In this task, you'll update the pattern using curly brackets instead of the + symbol. In regular expressions, curly brackets can be used to represent an exact number of repetitions between two numbers. For example, {2,4} in a regular expression means between 2 and 4 occurrences of something. Applying this to an example, \w{2,4} would match with two, three, or four alphanumeric characters. Afterwards, you'll call the re.findall() function on the updated pattern and the log_file and store the output in a variable named valid_ip_addresses.

Then, display the contents of valid_ip_addresses and run the cell to analyze the results. Be sure to replace each ### YOUR CODE HERE ### with your own code before you run the following cell.

<img src="https://i.imgur.com/Hb2zMjH.png" height="80%" width="80%"/>

<h3>Task 10</h3>

Now, all of the valid IP addresses have been extracted. The next step is to identify flagged IP addresses.

You're given a list of IP addresses that have been previously flagged for unusual activity, stored in a variable named flagged_addresses. When these addresses are encountered, they should be investigated further. This list is just for educational purposes and contains examples of private IP addresses that are found only within internal networks.

Display this list and examine what it contains by running the cell. Be sure to replace the ### YOUR CODE HERE ### with your own code before you run the following cell.

<img src="https://i.imgur.com/P92EFWg.png" height="80%" width="80%"/>

<h3>Task 11</h3>

Finally, you will write an iterative statement that loops through the valid_ip_addresses list and checks if each IP address is flagged. In the following code, the address will be the loop variable. Also, include a conditional that checks if the address belongs to the flagged_addresses list. If so, it should display "The IP address ______ has been flagged for further analysis." If not, it should display "The IP address ______ does not require further analysis." Be sure to replace each ### YOUR CODE HERE ### with your own code before you run the following cell.

<img src="https://i.imgur.com/8NkPACt.png" height="80%" width="80%"/>
