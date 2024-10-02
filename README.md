<h1>File permissions in Linux</h1>

<h2>Description</h2>
In this lab, I need to update the file permissions for certain files and directories within the projects directory. The permissions do not currently reflect the level of authorization that should be given. Checking and updating these permissions will help keep the system secure. Let me know if you have any questions!

<h2>Languages and Utilities Used</h2>

- <b>Linux</b> 

<h2>Environments Used </h2>

- <b>Linux</b>
<h2>Project</h2>
<h3>Check file and directory details</h3>
<p align="center">
The following code demonstrates how I used Linux commands to determine the existing permissions set for a specific directory in the file system.
 <br/>
<img src="https://i.imgur.com/lOmje6d.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
The first line of the screenshot displays the command I entered, and the other lines display the output. The code lists all contents of the projects directory. I used the ls command with the -la option to display a detailed listing of the file contents that also returned hidden files. The output of my command indicates that there is one directory named drafts, one hidden file named .project_x.txt, and five other project files. The 10-character string in the first column represents the permissions set on each file or directory.<br/>
<h3>Describe the permissions string</h3>
<p align="center">
<br/> The 10-character string can be deconstructed to determine who is authorized to access the file and their specific permissions. The characters and what they represent are as follows:
<b>1st character: This character is either a d or hyphen (-) and indicates the file type. If it’s a d, it’s a directory. If it’s a hyphen (-), it’s a regular file.</b>
<b></b>2nd-4th characters: These characters indicate the read (r), write (w), and execute (x) permissions for the user. When one of these characters is a hyphen (-) instead, it indicates that this permission is not granted to the user.
<b></b>5th-7th characters: These characters indicate the read (r), write (w), and execute (x) permissions for the group. When one of these characters is a hyphen (-) instead, it indicates that this permission is not granted for the group.
<b></b>8th-10th characters: These characters indicate the read (r), write (w), and execute (x) permissions for other. This owner type consists of all other users on the system apart from the user and the group. When one of these characters is a hyphen (-) instead, that indicates that this permission is not granted for other.
<br/>
<img src="https://i.imgur.com/zX7FWe8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
When using an .open() function that includes the argument "r" for “read,” I can call the .read() function in the body of the with statement. The .read() method converts the file into a string and allows me to read it. I applied the .read() method to the file variable identified in the with statement. Then, I assigned the string output of this method to the variable ip_addresses. 
 <br/>
  <br/> In summary, this code reads the contents of the "allow_list.txt" file into a string format that allows me to later use the string to organize and extract data in my Python program.
<br/>
<h3>Convert the string into a list</h3>
  <p align="center">
<br/> In order to remove individual IP addresses from the allow list, I needed it to be in list format. Therefore, I next used the .split() method to convert the ip_addresses string into a list: <br/>
<img src="https://i.imgur.com/Ucb9vn6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
The .split() function is called by appending it to a string variable. It works by converting the contents of a string to a list. The purpose of splitting ip_addresses into a list is to make it easier to remove IP addresses from the allow list. By default, the .split() function splits the text by whitespace into list elements. In this algorithm, the .split() function takes the data stored in the variable ip_addresses, which is a string of IP addresses that are each separated by a whitespace, and it converts this string into a list of IP addresses. To store this list, I reassigned it back to the variable ip_addresses. 
<br/>
<h3>Iterate through the remove list</h3>
  <p align="center">  
 <br/>A key part of my algorithm involves iterating through the IP addresses that are elements in the remove_list. To do this, I incorporated a for loop:<br/>
<img src="https://i.imgur.com/Hyihozk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
The for loop in Python repeats code for a specified sequence. The overall purpose of the for loop in a Python algorithm like this is to apply specific code statements to all elements in a sequence. The for keyword starts the for loop. It is followed by the loop variable element and the keyword in. The keyword in indicates to iterate through the sequence ip_addresses and assign each value to the loop variable element. 
<br/>
<h3>Remove IP addresses that are on the remove list</h3>
  <p align="center">  
<br/>My algorithm requires removing any IP address from the allow list, ip_addresses, that is also contained in remove_list.  Because there were not any duplicates in ip_addresses, I was able to use the following code to do this: <br/>
<img src="https://i.imgur.com/gLBH4ux.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
First, within my for loop, I created a conditional that evaluated whether or not the loop variable element was found in the ip_addresses list. I did this because applying .remove() to elements that were not found in ip_addresses would result in an error. 
<br />
<br/>Then, within that conditional, I applied .remove() to ip_addresses. I passed in the loop variable element as the argument so that each IP address that was in the remove_list would be removed from ip_addresses.<br/>
<h3>Update the file with the revised list of IP addresses </h3>
  <p align="center"> 
<br/> As a final step in my algorithm, I needed to update the allow list file with the revised list of IP addresses. To do so, I first needed to convert the list back into a string. I used the .join() method for this:<br/>

<img src="https://i.imgur.com/gE1LSUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>The .join() method combines all items in an iterable into a string. The .join() method is applied to a string containing characters that will separate the elements in the iterable once joined into a string. In this algorithm, I used the .join() method to create a string from the list ip_addresses so that I could pass it in as an argument to the .write() method when writing to the file "allow_list.txt". I used the string ("\n") as the separator to instruct Python to place each element on a new line. <br/>
<p align="center"> 
<br/>Then, I used another with statement and the .write() method to update the file:<br/>
<img src="https://i.imgur.com/9RGlilW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>This time, I used a second argument of "w" with the open() function in my with statement. This argument indicates that I want to open a file to write over its contents. When using this argument "w", I can call the .write() function in the body of the with statement. The .write() function writes string data to a specified file and replaces any existing file content. <br/>
<p align="center"> 
<br/>In this case I wanted to write the updated allow list as a string to the file "allow_list.txt". This way, the restricted content will no longer be accessible to any IP addresses that were removed from the allow list. To rewrite the file, I appended the .write() function to the file object file that I identified in the with statement. I passed in the ip_addresses variable as the argument to specify that the contents of the file specified in the with statement should be replaced with the data in this variable.<br/>
<h3>Summary</h3>
  <p align="center"> 
<br/>I created an algorithm that removes IP addresses identified in a remove_list variable from the "allow_list.txt" file of approved IP addresses. This algorithm involved opening the file, converting it to a string to be read, and then converting this string to a list stored in the variable ip_addresses. I then iterated through the IP addresses in remove_list. With each iteration, I evaluated if the element was part of the ip_addresses list. If it was, I applied the .remove() method to it to remove the element from ip_addresses.. After this, I used the .join() method to convert the ip_addresses back into a string so that I could write over the contents of the "allow_list.txt" file with the revised list of IP addresses.<br/>


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
