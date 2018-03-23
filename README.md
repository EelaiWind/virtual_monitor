# Virtual Monitor Setup Manual

#### Goal: Add a virtual monitor on a server without a physical monitor. Make it possible to run the V-REP simulatior.

1. Download [dfp-edid.bin](https://drive.google.com/open?id=0B-KERIuNSvqab1ZBSWx4SF9aVzA) and put it at `/etc/dfp-edid.bin`. This file will act as a virtual monitor
2. Edit `/etc/X11/xorg.conf`. Add the following 3 line in each **Section “Screen”**
    ```
    Option    "UseDisplayDevice" "DFP-0"
    Option    "ConnectedMonitor" "DFP-0"
    Option    "CustomEDID" "DFP-0:/etc/dfp-edid.bin"
    ```
    * Configuration Example
    
    ![](https://i.imgur.com/KJPYsXj.png)

3. Restart X server  service
    * `sudo service lightdm restart`
        * Replace `lightdm` with different X server if necessary
