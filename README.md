# Run ArcadeDB as a service in Ubuntu

* Create a new service file in the directory ***/lib/systemd/system***. The naming convention can be like E.g.:- *arcadedb-server.service*
* The content of the file can be reference in the file added to this repository.
  1. WorkingDirectory = The home directory of the arcadedb release downloaded
  2. ExecStart= Use the arcadedb bin/server.sh script together with passing relevant arguments.
* **Commands**:
   1. systemctl daemon-reload  #use this command to apply latest service file changes
   2. systemctl enable {SERVICE_NAME}.service  #Enable the service to have it ready and started during system booting
   3. systemctl start {SERVICE_NAME}.service   #Start the service
   4. systemctl status {SERVICE_NAME}.service  #Status of the systemd service
   5. systemctl stop {SERVICE_NAME}.service    #Stop the service
   6. systemctl restart {SERVICE_NAME}.service #Restart the service
 
*  **Check the ArcadeDB service logs:**
   1. journalctl -u {SERVICE_NAME}.service --since today -b -f #Recommended
   2. tail -100 /var/log/syslog

**Note**:- 
 1. {SERVICE_NAME} - Replace with actual service name.
 2. Provide user credentials when password prompt is asked when systemd commands are used.
![image](https://github.com/devcode100/graphdb-space/assets/19166514/6f10e042-f94d-4f5c-93df-5e0f8cc14954)
