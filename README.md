# Use Linux commands to manage file permissions <br> - File permissions in Linux

## Objective

This project aimed to enhance the security posture of the project directory by implementing appropriate file and directory permissions. By leveraging Linux commands such as ls -la and chmod, the goal was to restrict access to sensitive files and directories, mitigating potential security risks.

## Project description
Our research team needed to tighten security permissions for specific files and directories within our project directory. To ensure the system's integrity, I reviewed the current permissions and made necessary adjustments. This involved:

## Skills Learned

**Technical Skills:**

* Linux Command Line: Proficiency in using basic Linux commands like ls, chmod, and cd to navigate the file system and modify permissions.
* File Permission Understanding: Knowledge of file permission syntax (rwx) and how to modify permissions using the chmod command.
* Security Best Practices: Awareness of security principles like least privilege and the importance of restricting file and directory access.

**Problem-Solving and Analytical Skills:**

* Identifying Security Risks: The ability to assess the security implications of file and directory permissions and identify potential vulnerabilities.
* Troubleshooting: The skill to diagnose permission-related issues and implement appropriate solutions.
* Critical Thinking: The capacity to evaluate different approaches to file permissions and select the most secure and practical method.

## Tools Used

The primary tool used in this project is the Linux command line. Specifically, the following commands were utilized:

* ls -la: This command lists files and directories in a long format, including permissions, owner, group, size, modification date, and filename. It's essential for understanding the current permissions of files and directories.
* chmod: This command is used to change file permissions. It allows for the modification reading, writing, and execute permissions for the owner, group, and others.

By effectively using these commands, I was able to:

* Assess current permissions: Identify any security vulnerabilities or misconfigurations.
* Modify permissions: Adjust permissions to align with security policies and protect sensitive data.
* Verify changes: Use the ls -la command to confirm that permissions were modified as intended.

These commands are fundamental to Linux system administration and security, and their effective use demonstrates understanding of file permissions and how to secure file systems.

## Steps
### **Check file and directory details**
Here's a breakdown of how I used Linux commands to determine the existing permissions set for a specific directory in the file system:<br>

![Linux 1](https://github.com/user-attachments/assets/09a9baaf-63c8-447d-ae50-81494b50bddd)<br>

The command prompt shows I ran the command "ls -la" to list all files and directories in the "projects" directory, including hidden files. The output displays a detailed list of files, including permissions, file size, modification date, and file name. The directory listing shows one directory named "drafts," one hidden file named ".project_x.txt," and five other project files.

### Describe the permissions string
File Permissions Breakdown:

The 10-character string representing file permissions can be broken down as follows:

1st Character:
* d: Directory
* -: Regular file

2nd-4th Characters: User Permissions
* r: Read permission
* w: Write permission
* x: Execute permission
* -: Permission denied

5th-7th Characters: Group Permissions (Same as user permissions)
* r: Read permission
* w: Write permission
* x: Execute permission
* -: Permission denied

8th-10th Characters: Other Permissions (Same as user permissions)
* r: Read permission
* w: Write permission
* x: Execute permission
* -: Permission denied

Example: -rw-rw-r--
* File Type: Regular file
* User Permissions: Read and write
* Group Permissions: Read and write
* Other Permissions: Read-only

### **Change file permissions**

To ensure compliance with the organization's security policy, I reviewed existing file permissions and identified that the 'other' user group had write access to 'project_k.txt'. To mitigate this risk, I removed the write permission for the 'other' group, effectively restricting file modification to authorized users. 

Here's a screenshot of the Linux commands I used to accomplish this:<br>

![Linux 2](https://github.com/user-attachments/assets/fcdc9769-1a12-42a7-b8a4-2becc9920a37)<br>

I executed the chmod command to modify the permissions of the project_k.txt file. Specifically, I removed write permissions for the 'other' user group. The subsequent ls -la command verified the successful implementation of the permission change.

### **Change file permissions on a hidden file**

The research team recently archived project_x.txt. They want to restrict write access while maintaining read permissions for the user and group.

To ensure the security of the archived project_x.txt file, I utilized Linux commands to adjust the file permissions. The following code snippet demonstrates how I implemented this change:<br>

![Linux 3](https://github.com/user-attachments/assets/e89ac97d-97e0-4908-a644-82e37b615b19)<br>

Here, I executed two commands to modify the permissions of the hidden file .project_x.txt. The first command, `chmod u-w,g-w,g+r .project_x.txt`, removed write permissions for both the user and group, and added read permissions for the group. The second command, `ls -la`, was used to verify the updated permissions.

### Change directory permissions
To ensure data security, I've implemented a file permission system that restricts access to the drafts directory exclusively to the researcher2 user. This prevents unauthorized access and maintains confidentiality. 

Here's a breakdown of the Linux commands I used to modify file permissions:<br>

![Linux 4](https://github.com/user-attachments/assets/7d40ba03-14bd-41f9-9b80-7079372b75d3)<br>

The output shows file and directory permissions. The current directory (projects) and its parent directory (home) have standard permissions. The .project_x.txt file has default permissions. The 'drafts' directory, however, had excessive permissions. I used the chmod command to restrict access to only the researcher2 user, who already had necessary permissions.

### Summary

I meticulously reviewed and adjusted file and directory permissions within the projects directory to align with organizational security standards. By leveraging the `ls -la` command, I gained a comprehensive understanding of existing permissions, enabling me to make informed decisions. The `chmod` command was instrumental in implementing the necessary adjustments, ensuring that access was granted only to authorized individuals.
