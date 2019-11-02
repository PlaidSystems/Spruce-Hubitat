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
    
**Install Overview**

*It is recommended to setup and name all zones before connecting Spruce and Hubitat*

**TODO**
Import the following files
