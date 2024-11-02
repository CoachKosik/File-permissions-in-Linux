# Use Linux commands to manage file permissions <br> - File permissions in Linux

## Objective

This project aimed to enhance the security posture of the project directory by implementing appropriate file and directory permissions. By leveraging Linux commands such as ls -la and chmod, the goal was to restrict access to sensitive files and directories, mitigating potential security risks.

## Project description
Our research team needed to tighten security permissions for specific files and directories within our project directory. To ensure the system's integrity, I reviewed the current permissions and made necessary adjustments. This involved:



## Skills Learned

1. **Network Traffic Analysis:**
   * Interpret network traffic logs, identifying protocols like TCP, UDP, HTTP, and ICMP.
   * Recognize patterns in network traffic data, such as SYN floods or unreachable ports, to identify potential security incidents.
   * Utilize tools like tcpdump to capture and analyze network traffic for investigation purposes.

2. **Incident Response Procedures:**
   * Understand the importance of identifying the type of cyberattack impacting a system.
   * Explain the technical details of specific attacks, such as SYN floods and DNS server issues.
   * Differentiate between different network protocols and their roles in security breaches.

3. **Security Best Practices:**
   * Identify security vulnerabilities, such as weak password policies or misconfigured firewalls.
   * Recommend appropriate remediation strategies for identified vulnerabilities.
   * Understand the importance of strong password policies, including password complexity, regular updates, and account lockout mechanisms.

4. **Technical Communication:**
   * Document technical information in a clear and concise manner for both technical and non-technical audiences.
   * Explain complex cybersecurity concepts in an understandable way.
   * Effectively structure incident reports, including sections for problem identification, analysis, and remediation.

5. **Digital Forensics:**
   * Familiar with collecting and preserving digital evidence for security investigations.
   * Analyze network traffic logs and other digital artifacts to identify the root cause of an incident.

## Tools Used
* **Log Analysis:** Examining logs from various sources like web servers, firewalls, and DNS servers can provide valuable insights into network activity and potential security incidents.
* **Source Code Analysis:** Examining the source code of websites and applications can help identify vulnerabilities or malicious code injected by attackers.


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

## Materials Provided
<a href="https://docs.google.com/document/d/12wldwY7MB49m1PgouLjjarlcc1Ty1pf3FqNOfK4RBQE/edit?usp=sharing">File permissions in Linux</a><br>
<a href="https://docs.google.com/document/d/1sBEeC5_8Uf_sHgOabpFd497VMQIm_Q3h/edit?usp=sharing&ouid=105064495821226407439&rtpof=true&sd=true">Current file permissions of the /home/researcher2/projects directory</a>
