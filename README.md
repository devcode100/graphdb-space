# Run ArcadeDB as a service in Ubuntu

* Create a new service file in the directory ***/lib/systemd/system***. The naming convention can be like E.g:- *arcadedb-server.service*
* The content of the file can be reference in the file added to this repository.
* **Commands**:
 1. systemctl daemon-reload  #use this command to apply latest service file changes
 2. systemctl enable {SERVICE_NAME}.service #enable the service to have it ready during host startup
 3. systemctl start {SERVICE_NAME}.service #Start the service
 4. systemctl status {SERVICE_NAME}.service #Status the service
 5. systemctl stop {SERVICE_NAME}.service #Stop the service
 6. systemctl restart {SERVICE_NAME}.service #Restart the service
 
*  **Check the ArcadeDB service logs:**
   1. journalctl -u {SERVICE_NAME}.service --since today -n 500 -f #Recommended
   2. tail -100 /var/log/syslog

**Note**:- {SERVICE_NAME} - Replace with actual service name
