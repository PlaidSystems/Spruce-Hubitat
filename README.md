# Spruce-Hubitat
*Connect Spruce GEN2 Wifi controller to Hubitat Elevation Hub

Integrate Spruce GEN2 Controller and GEN1, GEN2 or GEN3 Sensors with Hubitat. Control zones and manual schedules, pause or stop watering, recieve sensor readings, use Hubitat automations.

**Requires**
  - Spruce GEN2 Wifi Controller
  - Hubitat Elevation Hub
  
**Currently Hubitat and SmartThings can NOT be connected to the same account at the same time, the last linked integration will be the active connection**
  
**Installation**
  - App- Spruce Connect
  - Drivers- Spruce wifi master, Spruce wifi schedule, Spruce wifi zone
  
**Features**
  - Spruce Connect uses OAUTH2 to connect Hubitat to Spruce Cloud.
  - Master controller device with status, run all zones, pause and manual schedule controls
  - Child Zone devices with individual zone control and monitoring
  - Each zone and each manual schedule provided as "devices" that can be used as "switches" within standard ST automations and SmartApps
  - "Contacts" can be selected to pause/resume schedules
  - Pause device can be enabled and used in automations or Apps to pause/resume schedules
  - Schedule, zone and valve error notifications available
  - Valve health and flow (when used with flow meter)
  - Spruce sensors paired with Hubitat can use the Spruce Connect to report values to the Spruce Cloud.

 **Master Device Commands**
  - Off:    Stops all schedules or zones that are on
  - On:     Waters all zones for the duration specified by Set Level
  - Pause:  Pauses a schedule for up to 2 hours before cancelling the schedule
  - Resume: Resumes a paused schedule
  - Level:  Set the water time for each zone. This setting does not effect scheduled watering
  - Update Settings: Updates the manual schedule child device list from the Spruce Cloud

  **Schedule Device Commands**
  *Only Manual schedules can be started from Hubitat*
  - Off:    Stops the schedule
  - On:     Starts the schedule

  **Zone Device Commands**
  - Off:    Stops this specific zone, if the zone is on as part of a schedule, the next zone in sequence will start
  - On:     Waters the zone for the duration specified by Set Level
  - Refresh:Updates the zone attributes from the SPruce Cloud
  - Level:  Set the water time for the zone. This setting does not effect scheduled watering
    
**Code Install Overview**

*It is recommended to setup and name all zones before connecting Spruce and Hubitat*

Import each of the Drivers and App using the URLs listed below.
  1. Go to Drivers Code or Apps Code in your Hubitat account
  2. Add New Driver or App
  3. Import
  4. Copy and paste URL
  5. Save the Driver or App
  6. Repeat steps 1-5 for each file, being sure the Drivers Code is added to Drivers and the App code is added to Apps 

Drivers Code  
  - https://raw.githubusercontent.com/PlaidSystems/Spruce-Hubitat/master/drivers/Spruce%20wifi%20master.src
  - https://raw.githubusercontent.com/PlaidSystems/Spruce-Hubitat/master/drivers/Spruce%20wifi%20schedule.src
  - https://raw.githubusercontent.com/PlaidSystems/Spruce-Hubitat/master/drivers/Spruce%20wifi%20zone.src
  - https://raw.githubusercontent.com/PlaidSystems/Spruce-Hubitat/master/drivers/Spruce%20sensor.src
  
App Code
  - https://raw.githubusercontent.com/PlaidSystems/Spruce-Hubitat/master/apps/Spruce%20Connect.src
    
**Install Overview**

Install the User App called Spruce Connect and link your Spruce account to your Hubitat account. When completed, the Spruce Connect will create virtual devices for the Spruce Controller and zones as well as any manual schedules that hav ebeen created in the Spruce app.  The Spruce Conenct can also pass Spruce Sensor data from Hubitat to the Spruce Cloud for use in Spruce scehdules.

*If Spruce sensors will be connected to Hubitat, pair them now with the Spruse Sensor intructions below*   

  1. Go to **Apps** and **Add User App**
  2. Select the **Spruce Connect** app and follow the link to Login to Spruce to start the authorization process
  3. Login with your Spruce account
  4. Allow access to Hubitat
  5. If succesful, a page indicating **Your account is now connected to Hubitat** will appear
  6. Close this window, and go back to your Hubitat account
  7. Go back to **Apps** and **Add User App**
  8. Select the **Spruce Connect** app again
  9. The app should recognize that you have been granted access and skip straight to allowing setup to continue
  
**Spruce Connect Setup**

  1. Select your Spruce controller from the list and select next
  2. Select any Spruce sensors that are connected to Hubitat and should also report to Spruce Cloud
     - **You may come back and edit the Spruce Connect anytime to add sensors as needed**
  3. Select any contact sensors that should pause watering anytime they are activated
  4. Select Done to complete the installation
  
**Spruce Sensor**

  1. Disconnect the Spruce Sensor from the Spruce Gen2 Controller or other hubs.  For Gen2 and Gen3 sensors this is done by holding the      magnet to the sensor magnet pad until the sensor has disconnected from the hub.
     - *Note: The Spruce Sensor does not need to be removed from the Spruce App. After connecting to Hubitat, you may opt to send the data to Spruce App, and the data will associate with the exsisting Sensor in the App.*
  2. Go to your Hubitat hub on your PC, go to Devices and then *Discover Devices*, select Zigbee to start the search routine
  3. Tap the magnet to teh Spruce Sensor to start the pair process
  4. Hubitat should identify the Spruce Sensor and give your the option to name the sensor
  5. If the sensor is not discovered after 1 minute, check the following:
     - Sensor Driver Code has been added to your account
     - Restart your Hubitat hub
     - Reset(step 1) the Spruce Sensor and retry the process
  
