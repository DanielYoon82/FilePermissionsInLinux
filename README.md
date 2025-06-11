<h1>File permissions in Linux</h1>

<h2>Description</h2>
File permissions for certain files and directories needed to be updated within the projects directory of my organization. The research team found that permissions do not reflect the level of authorization that should be given. This is what I performed to complete this task.
<br />


<h2>Languages and Utilities Used</h2>

- <b>Linux</b> 

<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)

<h2>Program walk-through:</h2>

- <b>Check file and directory details</b> <br/>
Directory was changed with command cd projects. <br />
This will lead to /home/researcher2/projects. <br />
Contents and permissions for this directory will be displayed using command ls -l
: <br/>
<br />
<p align="center">
<img src="https://github.com/DanielYoon82/FilePermissionsInLinux/blob/main/images/LinuxDirectory.jpg" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<br />

- <b>Describe the permissions string</b> <br/>
The permissions string displays as follows:
<br />
<p align="center">
<img src="https://github.com/DanielYoon82/FilePermissionsInLinux/blob/main/images/PermissionsString.jpg" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<br />
<br />
This shows there are 5 permissions in the file directory. The 10-character string represents read (r), write (w), or execute (x) permissions for the user, group, and other for types of owners. <br />
<br />

- <b>Change file permissions</b> <br />
Write permissions in the projects directory is checked for owner type of other with command ls -l. <br />
project _k.txt has write permissions for other users. <br />The write permission for owner type of other will be removed using the command chmod o-w project_k.txt <br />
File project_m.txt is restricted and should not be readable or writable by the group or other, only the user. <br />
Command ls -l is inputted to list the contents of the current directory. <br />
It shows that group permissions of project_m.txt is read only. <br />
chmod g-r project_m.txt so that the read permission is removed. <br />
<br />

- <b>Change file permissions on a hidden file</b> <br />
.project_x.txt is a hidden file that should not be written by anyone.  <br/>
ls -la command shows the user and group have incorrect write permissions. <br />
chmod u-w, g-w, g+r .project_x.txt command now remove write permissions for both owners but allows group to have read permission.
<br />

- <b>Change directory permissions</b> <br />
Researcher2 should only be allowed to have access to the /home/researcher2/projects/drafts directory. <br/>
ls -l command is entered while in the projects directory and shows that group has access to execute permission. <br />
chmod g-x drafts command is entered to remove the owner group from permission.
<br />

- <b>Summary</b> <br />
Upon discovery of owners using the ls -l and ls -la command for read, write, and execute permissions, adjustments were made to to allow permissions for certain owners. By using the chmod command to add or remove access allowed permissions to be executed properly.  <br />
<br />
<br />
