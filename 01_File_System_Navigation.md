# <u> --------------------  Basic Linux Commands  --------------------  </u>

## These commands are used to interact with the operating system and perform tasks.


## 1. <u> Bash ls - List Directory Contents </u>

It is used to list the contents of a directory/folder.

This command can display files, directories and information about them.

      ls
         
The ls command has a variety of options to customize its output:

### a. Long Listing Format
      
      The ls -l option gives you detailed information about files and folders.
      
      It displays information such as:
      
      file permissions
      number of links
      owner name
      owner group
      file size
      time of last modification
      file or directory name
      
      This format is useful for getting a comprehensive overview of the file attributes.
      
      Example: Long Listing Format
      ls -l
      total 24232
      -rw-r--r-- 1 user 197609 23777028 Jan 15 20:38 Cosmere_RPG_Beta_Rules_Preview.pdf
      drwxr-xr-x 1 user 197609        0 Apr  9 07:46 images/
      -rw-r--r-- 1 user 197609      890 Apr  9 07:48 my_file.txt
      -rw-r--r-- 1 user 197609   305366 Apr  9 07:48 report.csv
      -rw-r--r-- 1 user 197609   720974 Apr  9 07:47 voiceover.wav

### b. Including Hidden Files

      The ls -a option includes hidden files in the listing.
      
      Hidden files in Unix/Linux systems start with a dot (e.g., .bashrc).
      
      This option is helpful when you need to view or manage configuration files that are not visible by default.
      
      Example: Including Hidden Files
      ls -a
      ./  ../  .my_secret_file  Cosmere_RPG_Beta_Rules_Preview.pdf
      images/  my_file.txt  report.csv  voiceover.wav

### c. Human-Readable Sizes
   
      The ls -h option makes file sizes easier to read by converting byte counts into kilobytes (K), megabytes (M), gigabytes (G), etc.
      
      This option is particularly useful when you want to quickly assess the size of files and directories without manually converting bytes.
      
      Example: Human-Readable Sizes
      ls -lh (long-listing and human readable format)
      total 24M
      -rw-r--r-- 1 user 197609  23M Jan 15 20:38 Cosmere_RPG_Beta_Rules_Preview.pdf
      drwxr-xr-x 1 user 197609    0 Apr  9 07:51 images/
      -rw-r--r-- 1 user 197609  890 Apr  9 07:48 my_file.txt
      -rw-r--r-- 1 user 197609 299K Apr  9 07:48 report.csv
      -rw-r--r-- 1 user 197609 705K Apr  9 07:47 voiceover.wav

### d. Sorting by Time

      The ls -t option sorts files and directories by modification time, with the most recently modified files first.
      
      This option is useful when you want to see the most recently updated files first.
      
      Example: Sorting by Time
      ls -t
      images/  my_file.txt  report.csv  voiceover.wav
      Cosmere_RPG_Beta_Rules_Preview.pdf

### e. Reverse Order

      The ls -r option reverses the order of the sort.
      
      When used in combination with other options like -t, it can display the oldest files first.
      
      This option is useful for reversing the default sorting behavior to meet specific needs.
      
      Example: Reverse Order
      ls -r
      voiceover.wav  report.csv  my_file.txt  images/
      Cosmere_RPG_Beta_Rules_Preview.pdf

### f. Recursive Listing

      The ls -R option lists directories and their contents recursively.
      
      This is useful for viewing the entire directory tree.
      
      Example: Recursive Listing
      ls -R
      ./images:
      1.png  2.png  3.png  4.png
      ./myfolder:
      my_file.txt  new_directory/

### g. Sort by Size

      The ls -S option sorts files by size, with the largest files first.
      
      This is helpful for quickly identifying large files in a directory.
      
      Example: Sort by Size
      ls -S
      Cosmere_RPG_Beta_Rules_Preview.pdf  voiceover.wav  report.csv
      copy_of_my_file.txt  my_file.txt  images/  myfolder/

### h. One File per Line

      The ls -1 option lists one file per line, which is useful for scripts or when piping output to other commands.
      
      Example: One File per Line
      ls -1
      Cosmere_RPG_Beta_Rules_Preview.pdf
      images/
      my_file.txt
      report.csv
      voiceover.wav

### i. Directories Only

      The ls -d option lists directories themselves rather than their contents.
      
      This is useful for seeing directory names without contents.
      
      Example: Directories Only
      ls -d */
      images//  myfolder//

### j. Append Indicator

      The -F option appends an indicator character to entries (e.g., / for directories, * for executables).
      
      Example: Append Indicator
      ls -F
      Cosmere_RPG_Beta_Rules_Preview.pdf  images/
      my_file.txt  report.csv  voiceover.wav

#### Note : We can also use multiple options at the same time

      example: la -a -l
      example: ls- ah

      
## <u> 2. Bash cd - Change Directory </u>
   
The cd command is used to change the current working directory/folder in the terminal.
   
To change to a specific directory, use cd directory_name.

      cd my_directory

The cd command supports several useful options for navigating directories:

### a. cd .. Option: Move Up One Directory Level

      The cd .. command lets you go to the folder above your current one.
      
      It's useful when you need to go to the parent folder.
      
      Example
      cd ..

### b. cd ~ Option: Change to Home Directory

      The cd ~ command takes you to your home directory, which is the default directory for your user account.
      
      This option is useful when you need to return to your starting point after navigating through various directories.
      
      Example
      cd ~

### c. cd - Option: Switch to Previous Directory

      The cd - command switches your working directory to the previous one you were in.
      
      This option is useful for toggling between two directories without needing to type their full paths repeatedly.
      
      Example
      cd -
      
### d. cd / Option: Change to Root Directory

      The cd / command takes you to the root directory of the file system.
      
      This option is useful when you need to access system-wide files or directories.
      
      Example
      cd /

#### Note : The cd command itself does not support combining options, but you can use it in conjunction with other commands to enhance navigation efficiency.

      For example, using cd with ls can quickly show you the contents of a directory you navigate to:
      
      Example: Change and List
      cd my_directory && ls
      copy_of_my_file.txt  Cosmere_RPG_Beta_Rules_Preview.pdf
      images/  my_file.txt  myfolder/  report.csv  voiceover.wav


## <u> 3. Bash pwd Command - Print Working Directory </u>

The pwd command shows you the full path of the folder you're currently in.

      pwd

The pwd command supports a few options to customize its output:

### a. -L Option: Logical Path

      The -L option shows the logical path, including any symbolic links.
      
      This is the default behavior of pwd.
      
      Example: Logical Path
      pwd -L
      /home/user/my_directory

### b. -P Option: Physical Path

      The -P option shows the physical path, resolving any symbolic links to their actual locations.
      
      This is useful when you need to know the exact physical directory structure.
      
      Example: Physical Path
      pwd -P

#### Note : Knowing which folder you're in is important when moving around the filesystem. It helps you make sure you're in the right place when running commands that use relative paths.

Common Use Cases for pwd

      Running Scripts: Make sure your script is using the right files and folders.
      Managing Files: Check where you are before copying or moving files to avoid mistakes.
      Fixing Problems: Knowing your current folder can help you solve path-related issues.


## <u> 4. Bash echo Command - Display Text </u>

The echo command is used to show a line of text or a variable's value in the terminal.

To display a simple message, use echo "message"

      echo "Hello Ravi!"

The echo command has several options to customize its output:

        -n - Don't add a new line at the end
        -e - Allow special characters like \n for new lines or \t for tabs etc.
        -E - Don't allow special characters (default)


## <u> 5. Bash cat Command - Concatenate and Display Files </u>

The cat command is used to show the content of files in the terminal.

You can also use it to combine multiple files into one.

To display the content of a file, use cat filename.

      cat my_file.txt

To edit the file and save:

      nano my_file.txt  #opens nano text editor and we can edit the file
      ctrl+o to save and press enter
      ctrl+x to exit 
        
To concatenate two files:

      cat my_file1.txt my_file2.txt > my_file.txt
   
The cat command has options to change how it shows text:

      -n - Add numbers to each line
      -b - Add numbers only to lines with text
      -s - Remove extra empty lines
      -v - Show non-printing characters (except for tabs and end of line)


## <u> 6. Bash cp - Copy Files and Directories </u>

The cp command is used to copy files and directories from one location to another

It's like making a duplicate of your file or folder.

To copy a file, use cp source_file destination_file

      cp my_file.txt copy_of_my_file.txt

The cp command has options to change how it works:

      -r - Copy all files and folders inside a directory
      -i - Ask before replacing files
      -u - Copy only if the source is newer
      -v - Verbose mode, show files being copied


## <u> 7. Bash mv Command - Move or Rename Files </u>

The mv command is used to move or rename files and directories.

It's like changing where a file is or what it's called.

To move a file, use mv source_file destination_directory

      mv my_file.txt /path/to/destination/

To rename a file, use mv old_name new_name

      mv old_name.txt new_name.txt

The mv command has several options to customize its behavior:

      -i - Ask before replacing files
      -u - Move only if the source is newer
      -v - Verbose mode, show files being moved


## <u> 8. Bash rm Command - Remove Files or Directories </u>

The rm command is used to remove files or directories.

we should be very careful, as removed files cannot be easily recovered.

To remove a file, use rm filename

      rm my_file.txt

The rm command has options to change how it works:

      -r - Delete a folder and everything inside it
      -i - Ask before deleting each file
      -f - Force delete without asking
      -v - Verbose mode, show files being removed

#### Note : rm is used to remove files. However, rmdir command is useful to remove directories/folders, and the options are same.

   
## <u> 9. Bash touch Command - Change File Timestamps and create empty file if doesn't exist </u>

The touch command is used to change file timestamps or create an empty file if it doesn't exist.

It's often used to create placeholder files or update timestamps for build systems.

To update the access and modification times of a file, use touch filename

      touch my_file.txt

The touch command has options to change how it works:

      -a - Update only when the file was last read
      -m - Update only when the file was last changed
      -t - Set the timestamp to a specific time
      -c - Do not create any files


## <u> 10. Bash mkdir Command - Make Directories/folders </u>

The mkdir command is used to create new directories.

It's a simple way to organize files into folders.

To create a new directory, use mkdir directory_name

      mkdir new_directory

The mkdir command has several options to customize its behavior:

      -p - Create parent directories as needed
      -v - Show a message for each created directory
      -m - Set file mode (permissions)


## <u> 11. Bash man Command - User Manual </u>

The man command is used to display the user manual of any command that can be run on the terminal.

It's a valuable resource for understanding command usage, options, and examples.

The basic syntax of the man command is:

      man [command] or we can directly give ls --help
    
The man command is commonly used to:
    
      Learn about command options and usage, understand command syntax and examples.
        
      Access detailed documentation for troubleshooting.


## <u> 12. Bash alias </u>

Aliases in Bash allow you to create shortcuts for long or frequently used commands. This makes it easier to execute complex commands with a simple keyword.

Creating Aliases
    
To create an alias, use the syntax alias name='command', where name is the shortcut you want to use, and command is the full command you want to run.

      Example: Simple Alias - List
      alias ll='ls -la'
      In this example, ll lists all files in long format.
        
      Example: Simple Alias - Git Status
      alias gs='git status'
      In this example, gs is a shortcut for git status.

Managing Aliases

      To view all current aliases, use the alias command without arguments.

      Example: Viewing Aliases
      alias
      alias ll='ls -l'
      alias gs='git status'

Removing Aliases

      To remove an alias, use unalias name.

      Example: Removing an Alias
      unalias gs
