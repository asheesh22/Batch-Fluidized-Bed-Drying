# Batch-Fluidized-Bed-Drying
Auto data acquire system

The files list here is for the data accquirement using RaspberryPi3.
1. Folders
   /Database              The MySQL script for create the database and init the base data
   /configuration         config the Raspberry Pi 3 as a WiFi AP and Run a web based APP using DJango
   /DJangoGenerated       The files and folders created by DJango framework
   /Library               The files import from SHT1x project, LCi2c Project and dygraph project
   /Source                The files writen in this Project

2. Setup
   2.1 Config the Raspberry Pi 3, following the introductions in /configuration
   2.2 merge the files in /Library and /Source, then copy them into the site folder created by Django, overwrite some exist files.
   2.3 Try it

3. Comments
   3.1 Sensor connection
       The sensor should be connected as below:
           SHT15 1st : SCK 38,   DATA 40,    VCC  01 ,GND  39
           SHT15 2nd : SCK 32,   DATA 36,    VCC  17 ,GND  34
           SHT15 3rd : SCK 35,   DATA 37,    VCC  04 ,GND  30
       DisplayScreen:  SCL 05  , SDA  03,    VCC  02 ,GND  06

   3.2 WiFi
       The AP's SSID is [ FluidbedDrying ] , password is 12344321
       The clients IP will be 10.32.0.xxx
       They can be modofied by the AP configuration.

   3.3 The status data in MySQL Database
       In the table dataCapture.statusTB
       If the row having key 'ENABLES' is 'NO', all operation will be DISABLED;
            Change it to 'YES', then the sample can be start and end

   3.4 Access
       http://10.32.0.1:8000/sensor 
