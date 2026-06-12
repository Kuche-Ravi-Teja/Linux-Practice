# <u> ---------- File Permissions & Ownership Commands ---------- </u>

### In Linux, everything is a file, and securing those files relies on two concepts,

  - Ownership (who owns the file)
  - Permissions (what they can do with it).

### Ownership : Every file has a specific User (owner), a Group (a collection of users) and Others (third-party) assigned to it.

### Permissions: A set of rules defining who can Read (r), Write (w), or Execute (x) a file. These permissions are split into three categories: Owner (u), Group (g), and Others (o).

### The 0-7 Numeric Shortcut (Octal Notation) Instead of typing r, w, x, Linux uses numbers. Each permission has a value.
  
  - 4 = Read ($r$)
  - 2 = Write ($w$)
  - 1 = Execute ($x$)
  - 0 = No permission

### By adding these numbers together, you get a single digit (0–7) for each category.
  - 7 ($4+2+1$) : Read, Write, and Execute
  - 6 ($4+2$) : Read and Write
  - 5 ($4+1$) : Read and Execute
  - 4 : Read only
  - 3 : ($3+1$) : Write and Execute
  - 2 : Write only
  - 1 : Execute only
  - 0 : No permissions
  
         Example: Permission 755 means, (owner, group, others)
                - 7 (Owner can do everything)
                - 5 (Group can Read & Execute)
                - 5 (Others can Read & Execute)

 
## <u> The 4 Essential Commands </u> 

### Assume a hypothetical file named report.txt


### 01. chmod (Change Mode)

  - Changes the permissions (the 0-7 numbers) of a file.
  - Common Option : -R (Recursive - applies changes to a folder and everything inside it.

        Example : Give the owner full access (7), and everyone else read-only access (4) to report.txt

        command : chmod 744 report.txt


### 02. chown (Change Owner)

  - Changes the user ownership of a file.
  - Common Option: -R (Recursive).

        Example: Change the owner of report.txt to a user named alex

        command : chown alex report.txt

### Note : You can change both owner and group at once using,

    chown alex:marketing report.txt


### 03. chgrp (Change Group)

  - Changes the group ownership of a file.
  - Common Option: -R (Recursive).
  
        Example: Change the group of report.txt to the marketing team.

        command : chgrp marketing report.txt

    
### 04. sudo (Superuser Do)
  
  - A prefix that lets you run commands with admin (root) privileges.
  - Because you cannot just change ownership of someone else's files, you use sudo to force it.
  - Common Option: -u [user] (Run the command as a specific user instead of root).

        Example: You try to change a file's owner but get "Permission Denied". You use sudo to override it.

        command : sudo chown alex report.txt
    
        (This will ask for your password to confirm you have admin rights).
