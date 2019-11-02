# Spruce-Hubitat
*Connect Spruce GEN2 Wifi controller to Hubitat Elevation Hub

Integrate Spruce GEN2 Controller and GEN1, GEN2 or GEN3 Sensors with Hubitat. Control zones and manual schedules, pause or stop watering, recieve sensor readings, use Hubitat automations.

**Requires**
  - Spruce GEN2 Wifi Controller
  - Hubitat Elevation Hub
  
**Installation**
  - App- Spruce Connect
  - Drivers- Spruce wifi master, Spruce wifi schedule, Spruce wifi zone
  
**Features**
  - Spruce Connect uses OAUTH2 to connect Hubitat to Spruce Cloud.
  - Master controller device with status, run all zones, pause and manual schedule controls
  - Child Zone devices with individual zone control and monitoring
  - Each zone and each manual schedule provided as "devices" that can be used as "switches" within standard ST automations and SmartApps
  - "Contacts" can be selected to pause/resume schedules
  - Pause device can be enabled and used in automations or SmartApps to pause/resume schedules
  - Schedule, zone and valve error notifications available
  - Valve health and flow (when used with flow meter)
  - Spruce sensors paired with Hubitat can use the Spruce Connect to report values to the Spruce Cloud.
    
**Code Install Overview**

*It is recommended to setup and name all zones before connecting Spruce and Hubitat*

Import the the Drivers and App using the URLs listed below.
  1. Go to Drivers Code or Apps Code in your Hubitat account
  2. Add New Driver or App
  3. Import
  4. Copy and paste the URL
  5. Save the Driver or App

Drivers Code  
  - https://raw.githubusercontent.com/PlaidSystems/Spruce-Hubitat/master/drivers/Spruce%20wifi%20master.src
  - https://raw.githubusercontent.com/PlaidSystems/Spruce-Hubitat/master/drivers/Spruce%20wifi%20schedule.src
  - https://raw.githubusercontent.com/PlaidSystems/Spruce-Hubitat/master/drivers/Spruce%20wifi%20zone.src
  
App Code
  - https://raw.githubusercontent.com/PlaidSystems/Spruce-Hubitat/master/apps/Spruce%20Connect.src
    
**Install Overview**

Install the User App called Spruce Connect and link your Spruce account to your Hubitat account. When completed, the Spruce Connect will create virtual devices for the Spruce Controller and zones as well as any manual schedules that hav ebeen created in the Spruce app.  The Spruce Conenct can also pass Spruce Sensor data from Hubitat to the Spruce Cloud for use in Spruce scehdules.

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
  2. Select and Spruce sensors that are connected to Hubitat and should also report to Spruce Cloud
  3. Select and contact sensors that should pause watering anytime they are activated
  4. Select Done to complete the installation
  
