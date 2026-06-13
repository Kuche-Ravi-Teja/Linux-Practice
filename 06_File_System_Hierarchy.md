# <u> -------------------- File System Hierarchy -------------------- </u> 

### In Linux, everything is treated as a file - even your keyboard, mouse, printer, and hard drives. Because of this, Linux organizes its directories in a single, unified tree structure called the Filesystem Hierarchy Standard (FHS).

### If you are coming from Windows, think of it this way: instead of having separate roots for different drives (like C:\ and D:\), Linux places everything inside one single trunk called the root directory, represented by a single forward slash (/).

## <u> The Linux Directory Tree Overview </u>
  
### Here is a simple, professional breakdown of every major directory sitting directly under the root (/) and what it actually does.

### 1. / (The Root)
  
  - What it is: The absolute starting point of the entire filesystem. Every single directory and file on your computer lives inside this root directory.

  - Analogy: The foundation of the entire building.

### 2. /bin (Essential User Binaries)

  - What it is: Contains the fundamental command-line programs (binaries) that are required for the system to boot and run in single-user mode.

  - What lives here: Basic everyday commands like ls, cp, mv, ping, and ps.

### 3. /sbin (System Binaries)

  - What it is: Similar to /bin, but these programs are meant for system administrators. These commands are used for system maintenance, booting, and repairs.

  - What lives here: Advanced tools like ifconfig, fdisk, reboot, and iptables.

### 4. /etc (Editable Text Configuration)

  - What it is: The nerve center for system configuration. It contains text files that control how the operating system and various software packages behave. If you need to change a system setting (like your network setup or user passwords), you look here.

  - What lives here: /etc/passwd (user accounts), /etc/hostname (computer name), and server configurations.

### 5. /home (User Home Directories)
             
  - What it is: This is the personal space for the regular users on the system. Inside /home, every user gets their own dedicated folder to store personal documents, downloads, desktop items, and configurations.

  - What lives here: If your username is kumar, your files live in /home/kumar.

  - Note: Regular users only have permission to modify files inside their own home directory.

### 6. /root (The Administrator's Home)
              
What it is: The personal home directory for the Root User (the system's absolute super-administrator). It is kept separate from regular users in /home to ensure the system can still log in and troubleshoot even if the secondary storage where /home sits is unmounted or broken.

### 7. /var (Variable Data)
                                                           
  - What it is: Short for "variable." This directory handles files that are constantly growing, shrinking, or changing while the system runs.

  - What lives here: System log files (/var/log), mail queues, print queues, and web server databases.

### 8. /usr (User System Resources)
                                                           
  - What it is: Historically stood for "User," but today it functions as the secondary hierarchy for user applications and shared data. It is often the largest directory on a Linux system because it holds programs installed by choice, rather than essential system tools.


## <u> Key Subdirectories </u>

### /usr/bin: Non-essential companion commands (e.g., Python, Git, standard text editors).

### /usr/local: Where programs you compile or install manually from source code live (safely away from automatic system updates).

### 9. /opt (Optional Software)
                                                           
  - What it is: Reserved for installing add-on, proprietary, or third-party software packages that don't split their files across the standard Linux directories. They bundle everything into a single folder here.

  - What lives here: Applications like Google Chrome, Discord, or large enterprise software suites.

### 10. /boot (Static Boot Loader Files)
                                                           
  - What it is: Contains the crucial files required to start up the operating system. It holds the Linux Kernel itself, configuration data, and the bootloader (like GRUB).

### 11. /dev (Device Files)
                                                           
  - What it is: Remember how "everything is a file" in Linux? This directory holds special files that represent your actual hardware components. Writing data to a file here sends data directly to a piece of hardware.

  - What lives here: /dev/sda (your primary hard drive), /dev/audio, or /dev/usb.

### 12. /proc & /sys (Virtual/Pseudo Filesystems)
                                                           
  - What they are: These directories don't actually exist on your hard drive; they are created dynamically in RAM by the Linux kernel. They act as a real-time window into the brain of your operating system.

  - /proc (Process Information): Tracks running processes and hardware configurations (e.g., /proc/cpuinfo tells you your CPU specs).

  - /sys (System Information): Allows you to interact with and configure hardware drivers and kernel subsystems directly.

### 13. /mnt & /media (Mounting Points)
                                                           
  - What they are: Temporary spaces used to make external storage devices accessible.

  - /media: Used by modern operating systems to automatically mount removable media like USB drives or external hard drives when you plug them in.

  - /mnt: A clean folder intended for administrators to manually mount storage drives or network shares temporarily.

### 14. /tmp (Temporary Files)
                                                           
  = What it is: A playground for programs to store temporary data they need right now but won't need later. Most Linux distributions completely wipe this directory every time the computer reboots.

### 15. /lib & /lib64 (Shared Libraries)
                                                           
  - What it is: Contains essential shared libraries (similar to .dll files in Windows) that the programs in /bin and /sbin need to execute properly.

                                                           
## <u> Why Is It Designed This Way? </u>
                                                           
  - The main reason for this rigid structure is portability, security, and predictability. Because every Linux system follows the Filesystem Hierarchy Standard, a DevOps engineer, system administrator, or developer can hop onto an Ubuntu cloud server, a Red Hat enterprise server, or an embedded Raspberry Pi and know exactly where the configuration files are, where the logs are stored, and where user data lives.
