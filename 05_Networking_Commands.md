# <u> -------------------- Networking Commands -------------------- </u>

## <u> Networking commands are specialized tools used in a Command Line Interface (CLI) to interact with, troubleshoot, and manage how your computer talks to other computers over a network (like the internet or a local office network). </u>

## Key Uses:

  - Troubleshooting Connectivity : Checking if a remote server or website is up or down.

  - Data Transfer : Downloading files from the internet or securely transferring files between systems.

  - Network Auditing : Viewing your own device's IP addresses and active network connections.

  - Remote Management : Securely logging into and controlling a computer located somewhere else in the world.

## <u> Essential Networking Commands </u>


### 01. ping (Packet Internet Groper)

  - Definition : Sends a small test packet of data to a specific network address (IP address or domain name) and waits for a response. It is used to check if a remote machine is online and how fast the connection is.

  - Options :

        -c [count]: Stops after sending a specific number of packets (by default, Linux will ping forever until you stop it).
        
        -i [interval]: Changes the wait time between sending each packet (in seconds).

  - Examples:
          
        - Standard check (4 times):
          
                ping -c 4 google.com
            
        - Fast troubleshooting check (send packets every 0.5 seconds to a local gateway):
          
                ping -c 5 -i 0.5 192.168.1.1


### 02. curl (Client URL)

  - Definition : A tool used to transfer data to or from a network server. In simple terms, it lets you download a webpage's raw source code or talk to web APIs directly from your terminal.

  - Options :

        -I (Capital i): Fetches only the HTTP header information (status codes like 200 OK or 404 Not Found) instead of the full webpage content.
        
        -o [filename]: Saves the downloaded output into a specific file instead of printing it on the screen.

  - Examples:

        Check if a website's server is responding correctly:

            curl -I https://www.example.com

        Download a weather API response directly to a JSON file:

            curl -o weather_data.json https://api.weather.com/v1/status


### 03. netstat (Network Statistics)

  - Definition : Displays active network connections, routing tables, and interface statistics. It helps you see exactly who your computer is talking to and what ports are open.

  - Options:

        -t: Shows TCP connections (the standard protocol for web traffic).
        
        -u: Shows UDP connections (used for streaming/gaming traffic).
        
        -l: Shows only the ports that are currently "listening" for incoming connections.
        
        -n: Shows numerical addresses and port numbers instead of resolving them to names (makes the command run much faster).

  - Examples:

        List all active TCP and UDP connections numerically:
        
          netstat -tun
        
        Find out which ports are open and listening for incoming traffic:
        
          netstat -tln


### 04. ssh (Secure Shell)

  - Definition : Allows you to securely log into and control a remote Linux computer or server over an encrypted connection. Once logged in, anything you type runs on that remote machine.

  - Options:

        -p [port]: Connects to a non-standard port (by default, SSH uses port 22 for security).
        
        -i [identity_file]: Uses a specific private key file (like an .pem or .id_rsa file) for authentication instead of a password.
        
  - Examples:

        Connect to a remote server with a custom port:
        
            ssh -p 2222 admin@192.168.1.50
        
        Connect to a cloud server (like AWS) using a security key:
        
            ssh -i my-cloud-key.pem ubuntu@34.200.45.12


### 05. wget (World Wide Web Get)

  - Definition : A dedicated command-line file downloader. Unlike curl which is designed to move data flexibly, wget is built strictly to download files, installers, or entire websites in the background.

  = Options :

    -c: Resumes a partially downloaded file if the connection was dropped earlier.
    
    -b: Runs the download in the background so you can keep using your terminal.
    
  - Examples:

        Safely resume a huge database file download that timed out:
        
            wget -c https://example.com/large-dataset.zip
        
        Download a software installer in the background:
        
            wget -b https://downloads.apache.org/tomcat/tomcat-10.tar.gz


### 06. scp (Secure Copy Protocol)

- Definition : Allows you to securely copy files or folders between your local computer and a remote server (or between two remote servers) using the same secure encryption as SSH.

- Options :

      -P [port] (Capital P): Specifies a custom SSH port on the remote machine.
      
      -r: Recursively copies an entire directory/folder (not just a single file).

- Examples:

      Upload a local configuration file to a remote server's backup directory:
      
          scp config.json user@192.168.1.100:/home/user/backup/
      
      Download an entire folder of logs from a remote server using a custom port:
      
          scp -P 2222 -r user@192.168.1.100:/var/log/nginx/ ./local_logs/


### 07. rsync (Remote Sync)

  - Definition : An advanced file-copying tool that synchronizes files between two locations. It is incredibly efficient because it checks the differences between files and only copies the parts that changed, saving massive amounts of network bandwidth.

  - Options :

        -a (Archive mode): Preserves file permissions, timestamps, and symlinks so the copies are identical.
        
        -v (Verbose): Shows exactly which files are being copied in real time.
        
        -z: Compresses the data during transmission to speed things up.
        
        --delete: Deletes files in the destination folder if they no longer exist in the source folder (keeps them perfectly mirrored).

- Examples:

      Efficiently back up a project directory to a remote server with compression:
      
          rsync -avz /home/user/my_project/ user@192.168.1.105:/backup/project/
      
      Create an exact mirror backup, deleting old files on the backup server:
      
          rsync -av --delete /local/data/ user@192.168.1.105:/remote/data/


### 08. ifconfig (Interface Configuration)

  - Definition : Used to display or configure your system's network interfaces (like your Ethernet card or Wi-Fi card). It shows your current local IP address, subnet mask, and network hardware details.

  - Note: In newer Linux versions, the ip a command is replacing ifconfig, but ifconfig remains widely used).

  - Options :

        [interface]: Specifying an interface name (like eth0 or wlan0) isolates the details for just that specific network card.
        
        up / down: Turns a network interface completely on or off.

  - Examples:

        View network details for just the wireless network card:
        
          ifconfig wlan0
        
        Quickly restart an Ethernet connection to fix a local connection glitch:
        
          sudo ifconfig eth0 down && sudo ifconfig eth0 up
