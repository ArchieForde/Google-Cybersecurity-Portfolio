
# Using the Linux Command Line Interface to manage file permissions

## Objective

To demonstrate proficiency in managing file permissions and access control on Linux systems by utilizing fundamental Linux commands such as chmod. This project showcases the ability to configure secure file and directory permissions, ensuring appropriate access for users and groups while maintaining system security and integrity.

### Skills Learned

- Understanding the Linux file permission system, including read, write, and execute permissions for users, groups, and others.
- Practical use of the chmod command to modify file and directory permissions using symbolic and numeric modes.
- Applying permission changes to secure files and directories effectively.
- Developing a foundational understanding of access control in Linux environments.

## Case Study

You are a security professional at a large organization. You mainly work with their research team. Part of your job is to ensure users on this team are authorized with the appropriate permissions. This helps keep the system secure. 

Your task is to examine existing permissions on the file system. You’ll need to determine if the permissions match the authorization that should be given. If they do not match, you’ll need to modify the permissions to authorize the appropriate users and remove any unauthorized access.

## Report + Documentation

### Check file and directory details

<img width="806" alt="Screenshot 2025-01-16 at 23 17 43" src="https://github.com/user-attachments/assets/99b87ab5-df12-43d1-9401-dc64e59eb838" />

The first line of the screenshot displays the command I entered, and the other lines display the output. The code lists all contents of the projects directory. I used the ls command with the -la option to display a detailed listing of the le contents that also returned hidden files. The output of my command indicates that there is one directory named drafts, one hidden file named .project_x.txt, and five other project files. The 10-character string in the first column represents the permissions set on each file or directory.

### Describe the permissions string

<img width="128" alt="Screenshot 2025-01-16 at 23 17 13" src="https://github.com/user-attachments/assets/f006ce07-8f31-41a4-baaa-57b411f4491c" />

The 10-character string can be deconstructed to determine who is authorized to access the file and their specific permissions. The characters and what they represent are as follows:

- 1st character: This character is either a d or hyphen (-) and indicates the file type. If it’s a d, it’s a directory. If it’s a hyphen (-), it’s a regular file.

- 2nd-4th characters: These characters indicate the read (r), write (w), and execute (x) permissions for the user. When one of these characters is a hyphen (-) instead, it indicates that this permission is not granted to the user.

- 5th-7th characters: These characters indicate the read (r), write (w), and execute (x) permissions for the group. When one of these characters is a hyphen (-) instead, it indicates that this permission is not granted for the group.

- 8th-10th characters: These characters indicate the read (r), write (w), and execute (x) permissions for other. This owner type consists of all other users on the system apart from the user and the group. When one of these characters is a hyphen (-) instead, that indicates that this permission is not granted for other.

For example, the file permissions for project_t.txt are -rw-rw-r--. Since the first character is a hyphen (-), this indicates that project_t.txt is a file, not a directory. The second, fifth, and eighth characters are all r, which indicates that user, group, and other all have read permissions. The third and sixth characters are w, which indicates that only the user and group have write permissions. No one has execute permissions for project_t.txt.

### Change file permissions

The organization determined that other shouldn't have write access to any of their files. To comply with this, I referred to the file permissions that I previously returned. I determined project_k.txt must have the write access removed for other.

The following code demonstrates how I used Linux commands to do this:

<img width="806" alt="Screenshot 2025-01-16 at 23 40 14" src="https://github.com/user-attachments/assets/1a6fc6c6-32d8-4627-9034-ab7068af9b15" />

The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command. The chmod command changes the permissions on files and directories. The first argument indicates what permissions should be changed, and the second argument specifies the file or directory. In this example, I removed write permissions from other for the project_k.txt file. In the above photo it shows the difference after I used the chmod command.

### Change file permissions on a hidden file

The research team at my organization recently archived project_x.txt. They do not want anyone to have write access to this project, but the user and group should have read access. 

The following code demonstrates how I used Linux commands to change the permissions:

<img width="806" alt="Screenshot 2025-01-16 at 23 43 13" src="https://github.com/user-attachments/assets/75400fd7-f823-41d8-a824-c43e984df78e" />

The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command. I know .project_x.txt is a hidden file because it starts with a period (.). In this example, I removed write permissions from the user and group, and added read permissions to the group. I removed write permissions from the user with u-w. Then, I removed write permissions from the group with g-w, and added read permissions to the group with g+r. As shown below:

<img width="806" alt="Screenshot 2025-01-16 at 23 47 30" src="https://github.com/user-attachments/assets/a65df50a-ee86-49c7-8180-2c03a82076be" />

### Change directory permissions

My organization only wants the researcher2 user to have access to the drafts directory and its contents. This means that no one other than researcher2 should have execute permissions.

The following code demonstrates how I used Linux commands to change the permissions:

<img width="806" alt="Screenshot 2025-01-16 at 23 49 22" src="https://github.com/user-attachments/assets/07419d7a-db8c-4525-85ea-f315d5169515" />

The output here displays the permission listing for several files and directories. Line 1 indicates the current directory (projects), and line 2 indicates the parent directory (home). Line 3 indicates a regular file titled .project_x.txt. Line 4 is the directory (drafts) with restricted permissions. Here you can see that only researcher2 has execute permissions.  It was previously determined that the group had execute permissions, so I used the chmod command to remove them. The researcher2 user already had execute permissions, so they did not need to be added.

### Summary

I changed multiple permissions to match the level of authorization my organization wanted for files and directories in the projects directory. The first step in this was using ls -la to check the permissions for the directory. This informed my decisions in the following steps. I then used the chmod command multiple times to change the permissions on files and directories.










