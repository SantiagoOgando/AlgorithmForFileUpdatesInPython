<h1>Algorithm For File Updates In Python</h1>

<h2>Project Description</h2>
I am a security professional working at a health care company. Part of my job is updating a file that determines who has access to restricted content. I have been tasked to create an algorithm using Python that checks the allow list to see if there are any ip addresses that are also on the remove list.

<br />

<h2>Open the file that contains the allow list:</h2>
For the first part of the algorithm, I opened the "allow_list.txt" file. First, I assigned this file name as a string to the import_file variable:

**Import_file = “allow_list.txt”**

Then, I used a with statement to open the file:

**With open(import_file, “r”) as file:**

In my algorithm, the with statement is utilized in conjunction with the .open() function set to read mode to open the allow list file for reading. The primary objective is to access the IP addresses stored in the allow list file. The with keyword aids in resource management by automatically closing the file upon exiting the with statement. In the code snippet with open(import_file, "r") as file:, the open() function takes two parameters. The first identifies the file to import, and the second indicates the intended operation on the file. Here, "r" signifies a read operation. The as keyword is employed to assign a variable named file, which holds the output of the .open() function while operations are conducted within the with statement.

<h2>Read The File Contents:</h2>
In order to read the file contents, I used the .read() method to convert it into the string.

**ip_addresses = file.read()**

When utilizing the `.open()` function with the "r" argument for reading, I employ the `.read()` method within the `with` statement. This method transforms the file content into a string, facilitating subsequent operations in my Python script. The outcome of the `.read()` method applied to the file variable within the `with` statement is then assigned to the variable `ip_addresses`.

In essence, this code extracts the content of the "allow_list.txt" file as a string, providing a structured format for organizing and extracting data in my Python application.

<h2>Convert The String Into A List:</h2>
In order to remove individual IP addresses from the allow list, I needed it to be in list format. Therefore, I next used the .split() method to convert the ip_addresses string into a list:

**ip_addresses =  ip_addresses.split()**

Appending the `.split()` function to a string variable triggers its execution, converting the string's contents into a list. This operation serves the purpose of facilitating the removal of IP addresses from the allow list. By default, the `.split()` function segments the text into list elements based on whitespace. In this context, the `.split()` function takes the data from the `ip_addresses` variable, a string containing IP addresses separated by whitespace, and transforms it into a list of IP addresses. The resulting list is then reassigned to the variable `ip_addresses` for storage.

<h2>Iterate Through The Remove List:</h2>
A key part of my algorithm involves iterating through the IP addresses that are elements in the remove_list. To do this, I incorporated a for loop:

**for element in remove_list:**

In Python, the for loop is designed to iterate over a specified sequence, executing code for each element within that sequence. The primary objective of the for loop in this Python algorithm is to implement particular code statements for every element in a sequence. The for loop commences with the keyword "for," succeeded by the loop variable (element) and the "in" keyword. The "in" keyword signals the loop to iterate through the sequence of `ip_addresses` and assign each value successively to the loop variable, "element."

<h2>Remove IP Addresses That Are On The Remove List:</h2>
My algorithm requires removing any IP address from the allow list, ip_addresses, that is also contained in remove_list.  Because there were not any duplicates in ip_addresses, I was able to use the following code to do this:

**if element in ip_addresses:
	ip_addresses.remove(element)**

Initially, in the for loop, I introduced a condition to assess whether the loop variable "element" existed in the `ip_addresses` list. This check was necessary to prevent potential errors when using .remove(), as applying it to elements not present in `ip_addresses` could lead to issues.

Subsequently, within that conditional block, I employed .remove() on `ip_addresses`, specifying the loop variable "element" as the argument. This approach ensured that each IP address present in the `remove_list` would be successfully removed from the `ip_addresses` list.

<h2>Update The File With Revised List Of IP Addresses:</h2>
As a final step in my algorithm, I needed to update the allow list file with the revised list of IP addresses. To do so, I first needed to convert the list back into a string. I used the .join() method for this:

**ip_addresses = “\n”.join(ip_addresses)**

The .join() method is instrumental in merging all items within an iterable into a string. When employing the .join() method, a string containing characters that will act as separators between elements in the iterable is specified. In this specific algorithm, I utilized the .join() method to form a string from the list `ip_addresses`. This string was intended to be passed as an argument to the .write() method during the file-writing process for "allow_list.txt". The string ("\n") was chosen as the separator, indicating to Python that each element should be placed on a new line.

Subsequently, within another with statement, I utilized the .write() method to update the file:


**With open(import_file, “w”) as file:
	file.write(ip_addresses**

In this instance, I introduced a second argument, "w", when using the open() function within my with statement. The inclusion of this argument signifies my intention to open a file for writing, allowing me to overwrite its existing contents. With the "w" argument, I am able to invoke the .write() function within the with statement's body. The .write() function is designed to write string data to a designated file, completely replacing any pre-existing content.

In this specific scenario, my objective was to write the updated allow list as a string to the file "allow_list.txt". By doing so, any IP addresses removed from the allow list would no longer have access to the restricted content. To effect this rewrite, I appended the .write() function to the file object, which was denoted as `file` in the with statement. The ip_addresses variable was passed in as the argument, explicitly specifying that the contents of the file identified in the with statement should be substituted with the data stored in this variable.

<h2>Summary:</h2>
To summarize, I went through writing an algorithm that reads the allow_list.txt file and the remove_list. If there are any elements on the allow list that are also on the remove list, then the algorithm will know to remove them from the allow_list.txt file.


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
