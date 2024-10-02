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
<br/> The 10-character string can be deconstructed to determine who is authorized to access the file and their specific permissions. The characters and what they represent are as follows:<br/>
<p align="center">

- <b>1st character: This character is either a d or hyphen (-) and indicates the file type. If it’s a d, it’s a directory. If it’s a hyphen (-), it’s a regular file.</b>
- <b>2nd-4th characters: These characters indicate the read (r), write (w), and execute (x) permissions for the user. When one of these characters is a hyphen (-) instead, it indicates that this permission is not granted to the user.</b>
- <b>5th-7th characters: These characters indicate the read (r), write (w), and execute (x) permissions for the group. When one of these characters is a hyphen (-) instead, it indicates that this permission is not granted for the group.</b>
- <b>8th-10th characters: These characters indicate the read (r), write (w), and execute (x) permissions for other. This owner type consists of all other users on the system apart from the user and the group. When one of these characters is a hyphen (-) instead, that indicates that this permission is not granted for other.</b>
<p align="center">
<br/>
For example, the file permissions for project_t.txt are -rw-rw-r--. Since the first character is a hyphen (-), this indicates that project_t.txt is a file, not a directory. The second, fifth, and eighth characters are all r, which indicates that user, group, and other all have read permissions. The third and sixth characters are w, which indicates that only the user and group have write permissions. No one has execute permissions for project_t.txt.
<br />
<br/>
<h3>Change file permissions</h3>
  <p align="center">
<br/> The organization determined that other shouldn't have write access to any of their files. To comply with this, I referred to the file permissions that I previously returned. I determined project_k.txt must have the write access removed for other.<br/>
<br/> The following code demonstrates how I used Linux commands to do this:<br/>
<img src="https://i.imgur.com/vVjV6IW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command. The chmod command changes the permissions on files and directories. The first argument indicates what permissions should be changed, and the second argument specifies the file or directory. In this example, I removed write permissions from other for the project_k.txt file. After this, I used ls -la to review the updates I made.
<br/>
<h3>Change file permissions on a hidden file</h3>
  <p align="center">  
 <br/>The research team at my organization recently archived project_x.txt. They do not want anyone to have write access to this project, but the user and group should have read access.<br/>
<br/> The following code demonstrates how I used Linux commands to change the permissions:<br/>
<img src="https://i.imgur.com/zQ3dhT7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command. I know .project_x.txt is a hidden file because it starts with a period (.). In this example, I removed write permissions from the user and group, and added read permissions to the group. I removed write permissions from the user with u-w. Then, I removed write permissions from the group with g-w, and added read permissions to the group with g+r. 
<br/>
<h3>Change directory permissions</h3>
  <p align="center">  
<br/>My organization only wants the researcher2 user to have access to the drafts directory and its contents. This means that no one other than researcher2 should have execute permissions.<br/>
<br/> The following code demonstrates how I used Linux commands to change the permissions:<br/>
<img src="https://i.imgur.com/j8vmc3A.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
The output here displays the permission listing for several files and directories. Line 1 indicates the current directory (projects), and line 2 indicates the parent directory (home). Line 3 indicates a regular file titled .project_x.txt. Line 4 is the directory (drafts) with restricted permissions. Here you can see that only researcher2 has execute permissions.  It was previously determined that the group had execute permissions, so I used the chmod command to remove them. The researcher2 user already had execute permissions, so they did not need to be added.
<br />
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
