# <u> --------------- Process Management Commands --------------- </u>

## <u> Process Management is how an operating system (like Linux) juggles all the programs running on your computer. </u>

## Uses of Process Management

  - Performance Monitoring : Checking which programs are eating up your memory (RAM) or slowing down your processor (CPU).

  - Resource Allocation : Ensuring critical apps get the power they need while background tasks wait their turn.

  - Troubleshooting : Finding and freezing frozen, unresponsive, or "zombie" applications.

  - System Automation : Starting, stopping, or scheduling background services (like web servers) automatically.

## <u> Essential Linux Process Commands </u>

### 01. ps (Process Status)

  - Definition : Takes a snapshot of the processes currently running on your system. It's like a static photo of your system's activity at that exact millisecond.

  - Common Options : * -e or -A: Select all processes.

        -f : Does a "full format" listing, giving you extra details like who owns the process and when it started.

        aux : A very popular combination (no hyphen needed) that shows every process running on the system, regardless of who owns it.

            Simple Example:
    
                ps aux
                This will output a giant list of everything running, showing the User, Process ID (PID), %CPU, and %Memory usage.


### 02. top (Table of Processes)

  - Definition : Unlike ps, top provides a real-time, live-updating view of your running processes. It's like watching a live video stream of your CPU and RAM usage. The heaviest programs float to the top of the list automatically.

  - Common Options / Interactive Keys  :

        -d [seconds]: Changes the screen refresh delay (e.g., top -d 5 refreshes every 5 seconds).

While running, press q to quit, M to sort by memory usage, or P to sort by CPU usage.

            Simple Example:
              
              top
              Just type this to launch the live dashboard. It's the go-to command when your computer's fan starts spinning loudly and you want to see what is causing it.


### 03. free

  - Definition : This command displays the total amount of free and used physical memory (RAM) and swap memory in the system. It helps you quickly see if your computer is running out of breathing room.

  - Common Options :

        -m: Shows the memory numbers in Megabytes (MB).
        
        -g: Shows the memory numbers in Gigabytes (GB).
        
        -h: "Human-readable" mode; automatically chooses the best unit (MB or GB) so you don't have to do math.

          Simple Example:
          
            free -h
            Output might look like: Total: 16Gi, Used: 4.2Gi, Free: 8.5Gi. Quick, clean, and easy to read.


### 04. kill

  - Definition : Sends a signal to a specific process, usually to force it to shut down. If a program freezes and won't close normally, you use kill along with its Process ID (PID) to terminate it.

  - Common Options / Signals :

        -15 (SIGTERM): The polite request. It tells the app to save its data and close nicely (Default).
        
        -9 (SIGKILL): The absolute hammer. It forces the app to close instantly without saving anything.

          Simple Example:
          If a process (say, a buggy browser) has a PID of 1234:

             kill 1234
    
If it refuses to close:

            kill -9 1234

            
### 05. uptime

  - Definition : A quick, one-line command that tells you how long your computer has been running without a reboot. It also shows how many users are logged in and the system "load average" (how stressed the CPU has been over the last 1, 5, and 15 minutes).

  - Common Options :

        -p: "Pretty" mode. Shows the uptime in a much friendlier, human text format.
        
        -s: Shows the exact date and time the system started up.

          Simple Example:

            uptime -p
            Output example: up 2 weeks, 3 days, 5 hours, 14 minutes. Great for bragging about system stability!


### 06. systemctl (System Control)

  - Definition : The master controller tool. It is used to manage systemd services (background applications like your Wi-Fi manager, Bluetooth service, database, or web server). It allows you to start, stop, restart, or enable these services to launch automatically when the computer boots up.

  - Common Options (Commands) :

        start [service]: Starts a service.
        
        stop [service]: Stops a service.
        
        status [service]: Checks if a service is running or has errors.
        
        enable [service]: Sets the service to start automatically every time the computer turns on.

          Simple Example:
          If you are running an Apache web server and need to restart it after changing a setting:
          
            sudo systemctl restart apache2
            (Note: You usually need sudo / admin privileges for this command because it alters system-wide services).
