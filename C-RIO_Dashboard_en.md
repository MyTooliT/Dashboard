# (PART\*) [English] {-}

# Dashboard User Guide {-}
User guide for the ICOtronic Dashboard.

# Version
This user guide was written for Dashboard version v6.0.1.16. For older versions, use the link below:

[older version](https://github.com/MyTooliT/Dashboard/blob/main/Versions.md)

# ICOtronic System Components

The following diagram provides an overview of the components of the ICOtronic system. The main components are:

- Sensory Tool Holder (STH)
- Signal Processing Unit (SPU)
- Stationary Transceiver Unit (STU)

![Components](assets/Komponenten.png)

# Computer software and network settings

A computer with a Windows operating system (Windows 7 Service Pack 1; Windows 8.1 Update 1; Windows 10; Windows 11) and administrator rights is required. "LabView Runtime" must be installed on this computer.
Download link:

http://www.ni.com/download/labview-run-time-engine-2018/7383/en/

**ATTENTION: The 2021 SP1 (32-bit) version must be selected !!!**

The ICOtronicRemotePanel program must be used to connect to the dashboard.

Before connecting the computer to the SPU via Ethernet cable, the computer's network settings must be configured. To do this, the IP address of the computer that will be connected to the SPU must be set as follows.

![ip](assets/ip.png)

Then, if necessary, the computer should be restarted.

# Real-time dashboard

Open the "ICOtronicRemotePanel" to connect to the dashboard. The following window should now open and ask for the IP address of the dashboard. The following IP address must be entered here:
**192.168.42.115**

![Remote_IP](assets/Remote_IP.png)

Press "connect to SPU" to open the dashboard.

The dashboard should now open in a new window.
The dashboard has 6 tabs. Regardless of which tab is currently open, the header always remains the same.

![Header](assets/Bearbeitet/Top_bearbeitet.png)

T1: This indicator shows whether a holder is currently connected or not.
![Header](assets/Bearbeitet/Indikator-bearbeitet.png)
T2: When a connection to a holder is active, these fields display data such as the holder name and the MAC address of the connected holder.
T3: These are the various tabs that can display different information.
T4: This is the current date and time of the c-Rio. This can be changed in a sub-item of the "System" tab.
T5: This is the version number of the system.

## System tab

![System tab](assets/Bearbeitet/system_bearbeitet.png)

The System tab has 4 sub-modules:
S1: Connection module
S2: Rule & Sensor Configurations module
S3: Logging & Settings module
S4: Information module

### Connection Module

![Connection Module](assets/Bearbeitet/connection_bearbeitet.png)

This module (S1) contains information about the holder and rule selection and serves as a setting tool in the case of the "Dashboard Connection".
S47: This drop-down menu can be used to select the desired holder selection method.
S48: Pressing this button activates the selected holder selection method.
S49: This is the currently activated holder selection method.
S50: This list shows all holders currently visible via Bluetooth with their call names and MAC addresses.
S51: This identifier indicates whether the CAN connection with the STU is active.
S52: These tabs display information about the currently selected or connected holders.
S53: This button is used to issue a connection command via the "Dashboard". (This button only works if the corresponding checkbox in S33 has been selected).

#### Connection selection tab

##### Active

The "Active" tab in S52 provides more detailed information about the currently connected holder.

![active tab](assets/Bearbeitet/active.png)

##### Dashboard

![active tab](assets/Bearbeitet/DB_connection_bearbeitet.png)

The "Dashboard" tab is used to configure settings for the holder connection via the "Dashboard".
S54: Checkboxes to select up to 3 sensors and the alternative reference voltage.
S55: k-factors can be set here for the selected sensors.
S56: These are adjustable d-factors for the selected sensors.

##### DB cID

![active tab](assets/Bearbeitet/DB_cID_bearbeitet.png)

The "DB cID" tab is used to configure settings for the corresponding connection type.
S57: The desired connection ID can be specified here.
S58: The device and rule IDs associated with the connection ID selected in S57 are displayed here.

##### DB sID

![active tab](assets/Bearbeitet/DB_sID_bearbeitet.png)

The "DB sID" tab is used to configure settings for the corresponding connection type.
S59: The desired device ID can be specified here.
S60: The desired main rule can be specified here.
S61-S64: Up to 4 desired secondary rules can be specified here.

##### Digital Input cID

![active-tab](assets/Bearbeitet/digital-input-cid.png)

This tab contains information about the current settings that are currently applied via digital inputs in the corresponding connection type.

##### OPC-UA

![active tab](assets/Bearbeitet/opcua-conn.png)

This tab contains information about the current settings that are currently applied via OPC-UA in the corresponding connection type.

##### CNC

![cnc-tab](assets/Bearbeitet/cnc-conn.png)

This tab contains information about the current settings that are currently applied via a CNC interface in the corresponding connection type.

### Module Rule & Sensor Configurations

This submodule has 3 tabs

#### Rule Engine Configurations

![rules tab](assets/Bearbeitet/Rule_list_bearbeitet.png)

The current rules can be viewed and loaded here.
S10: This is a list of all current rules.
S11: The details of the rule currently selected in S10 are displayed here.
S12: This button can be used to load the rule currently selected in S10 into the nRT rules currently set in the dashboard.
S13: This button can be used to load the rule currently selected in S10 into the main rule currently set in the dashboard.

#### Device configs

![device tab](assets/Bearbeitet/sensor_list_bearbeitet.png)

Here, the currently loaded holders and their settings can be viewed and loaded into the dashboard connection.
S14: List of all loaded holder settings
S15: This button loads the holder settings selected in S14 into the connection settings of the "Dashboard" connection type.

#### Connect ID

![connect-id-tab](assets/Bearbeitet/Connection_list_bearbeitet.png)

This tab displays all configured connection IDs and their associated device and rule IDs, which can also be changed here.
S16: This list shows all currently configured connection IDs and their associated device and rule IDs.
S17: This button loads the IDs set in S18 into the connection ID currently selected in S16.
S18: These drop-down lists are used to set the IDs that are added to the list S16 using the S17 button. If the "delete" option is used for "Sensor", the selected ID is deleted from the list S16 when S17 is pressed. The main rule is able to control the overrides. The 4 nRT rules can only control the digital IOs. Their purpose is to indicate an intervention, but they do not have access to the analogue overrides.

### Module Logging & Settings

This module has 3 tabs

#### Logging

![logging tab](assets/Bearbeitet/Logging_bearbeitet.png)

In this tab, settings relating to data recording can be made.
S19: This button can be used to start or stop data recording.
S20: This identifier indicates whether data recording is desired via the digital IOs.
S21: This identifier indicates whether a USB stick is connected for data recording. **Please note: The system only works with USB devices that are formatted in FAT32 format!**
S22: This identifier indicates whether data recording is currently taking place.
S23: When data recording is active, the current size of the recording is displayed here.
S24: The available storage space on the connected USB stick is displayed here.
S25: An additional desired file name can be selected here, which is appended to the file name after the time stamp of the recording.
S26: A comment can be inserted here, which will be added to the file before recording begins.
S27: A comment can be inserted here, which will be added to the file at the end of the recording.
S28: A part number can be inserted here, which will be added to the file.
S29: Here you can insert an NC programme number, which will be inserted into the file.
S30: Here you can insert an employee number, which will be inserted into the file.

#### Settings

![settings tab](assets/Bearbeitet/Settings_bearbeitet.png)

Several settings can be configured in this tab. These include the methods that may be used to establish a connection.
S31: This setting can be used to configure the data rate of the OPC-UA connection.
S32: This display provides information about the most recent reading and writing processes.
S33: These checkboxes are used to allow the specified sources to trigger a connection. A connection can be established using any of the selected methods. As long as one of the methods wants a connection, the connection remains active. Only when all selected methods want to disconnect will the connection to the holder be interrupted. If "AutoConnect" is activated, a connection is triggered as soon as the selected holder is within range. If “AutoRecord” is activated, data recording starts automatically when a connection to a holder is established. If "Autoenable Rule" is activated, all rules are automatically activated when a connection is established.
S34: Here you can select the storage location for saving and loading configuration settings between c-Rio(local) and USB.
S35: This button saves the current connection list, holder selection settings, connection sources and other settings.
S36: This button overwrites the existing settings with those from the saved configuration file.
S37: This button can be used to trigger a reset of the STU.

#### System

![system-system tab](assets/Bearbeitet/system_system-bearbeitet.png)

The time and IP settings can be configured in this tab.
S38: A new system date and time can be specified here, which can be loaded with S40.
S39: This button opens a calendar that can be used to fill in S38.

![clock](assets/clock.png)

S40: This button overwrites the current system date and time with the data specified in S38.
S41: The time format used can be changed here.
S42: The current IP settings of the left (SYNC 0) LAN socket can be read out here.
S43: This button can be used to overwrite the current IP settings of the left (SYNC 0) LAN socket (S42) with the data from S45. This may cause the connection to be lost or the c-Rio to reboot.
S44: This button can be used to trigger a reboot of the c-Rio.
S45: Here you can specify IP settings that are to be applied to the left LAN socket (SYNC 0) with S43.
S46: Information about the change to the IP address is displayed here.

### Module Information

This module has 2 tabs

#### Signal Quality

![signal-quality-tab](assets/Bearbeitet/signal_quality_bearbeitet.png)

S5: The address of the c-Rio's OPC-UA server is displayed here.
S6: If there is an active connection to a holder, the battery voltage of the holder at the time the connection was established can be read here.
S7: If there is an active connection to a holder, a graph showing the signal quality is displayed here.

#### System Load

![system-load-tab](assets/Bearbeitet/CPU_load_bearbeitet.png)

S8: A graph of the CPU Load of the c-Rio can be seen here.
S9: The size of the available memory of the c-Rio can be read here.

### Holder selection methods

There are various ways in which the desired holder with the desired settings can be selected. The active type can be selected using S47 and S48 and read at S49. If the active holder selection method is changed using S48, the open tab S52 changes to the tab of the selected method.

![connection-list](assets/Bearbeitet/conn-list.png)

#### Dashboard

Here, the selected holder and sensors are selected using the dashboard, the S52 tab and the list of available holders S50. The rules applied are set and read directly in the C6 settings in the "Stability" tab.

#### Dashboard cID

Here, the desired holder and rules are selected from list S16 using their connection ID.

#### Dashboard sID

Here, the desired holder and rules are selected from list S14 using the device ID and from list S10 using the rule IDs.

#### Digital Input cID

Here, the desired holder and rules are selected from list S16 using the digital IOs.

#### OPC-UA

Here, the holder and rules are selected using the parameters set for the OPC-UA connection.

#### CNC

Here, the holder and rules are selected using a CNC interface.


## Database

![system](assets/Bearbeitet/Database_bearbeitet.png)

This tab is used to load and save the configuration of rules and sensors. It can be divided into three modules.
D1: The System module is used to load and save the set data.
D2: Here you can view a history of the activities carried out in this tab.
D3: The Sensor module is used to define the desired holders with their sensor selection.
D4: The Rule module is used to define the desired rules.
D5: This button can be used to delete the history in D2.
  

### System module

![system](assets/Bearbeitet/Database_control_bearbeitet.png)

This module is used to load and save the lists.
D6: Loads the lists currently applied on the c-Rio.
D7: Loads the lists into the c-Rio so that they can be actively used.
D8: Loads the lists stored locally on the c-Rio.
D9: Saves the lists locally on the c-Rio.
D10: Loads the lists from the source selected in D13 with the file name selected in D14.
D11: Saves the lists in the file selected in D14 on the medium selected in D13.
D13: Here you can select the medium on which the lists are read or written with D10 and D11.
D14: Here you can select the desired file name for reading and writing with D10 and D11.

### Sensor module

![system](assets/Bearbeitet/Database_devices_bearbeitet.png)

D15: The currently loaded list of devices and their settings is displayed here.
D16: This list shows all holders currently found in the environment.
D17: This button can be used to load the MAC address of the holder currently selected in D16 into the D23 settings field.
D18: The ID used to save the settings from D23 to D15 can be set here.
D19: Here you can enter the name of the setting that is displayed in list D15.
D20: This button can be used to delete the item currently selected in D15 from the list.
D21: This button can be used to load the settings of the item currently selected in D15 into the settings in D23.
D22: Here you can enter a description that will be displayed in the D15 list.
D23: Here you can enter the settings that will then be transferred to the list D15 by pressing the button D24.
The "Sensor Channels" drop-down menu is used to specify which channels the selected holder uses in this sensor entry.

![sensor selection](assets/sensorauswahl.png)

There are already a few predefined selections here. If a different sensor setting is desired, this can be entered using "Andere ...". Now a 16-bit binary input is required for the sensor selection. All "0"s before the first required "1" can be omitted. Sensor 1 is the LSB bit. For example, if sensors 1, 5 and 10 are to be selected, "1000010001" must be entered. The MSB defines the reference voltage. If a "1" is entered at the MSB position, the 1.8V reference voltage is used.
D24: This button transfers the values currently entered in D19, D22 and D23 to list D15, using the ID from D18.

### Module Rule

![system](assets/Bearbeitet/Database_rules_bearbeitet.png)

The rules applied can be set in this module.

D25: This is a list of all currently set rules.
D26: The details of the rule currently selected in D25 are displayed here.
D27: Here you can set the rule ID under which the settings are to be saved with D32.
D28: Here you can select the type of rule.
D29: Here you can select the base rule. If you select a rule other than "0", all parameters specified in D35 will load the parameters of the selected "base rule" if their value is set per the following list:

- mode: "from Baserule" option
- window length: 0
- upper/lower Threshold: <0
- ramp: 0
- stability Channel: "from Baserule" option
- minimum IFT level: <0
- deadtime: 0
- feed/spindle Override: >125
- feed/spindle Reduction Factor: >125
- low/high-pass filter: <0

This can be used if you want to use the same parameter from a predefined set and only need to change this rule to automatically change multiple rules.

D30: Here you can set the name of the rule, which will be transferred to list D25.
D31: Here you can enter a description of the rule, which will be transferred to list D25.
D32: This button transfers the data from D28-D31 and D35 to list D25.
D33: This button deletes the currently selected item from list D25.
D34: This button loads the settings of the currently selected item from list D25 into fields D27-D31 and D35.
D35: Here you can set the parameters of the rule.
A description of these parameters can be found in this manual in the chapter "Stability Tab".

## Replay tab

![system](assets/Bearbeitet/Replay_bearbeitet.png)

This tab is used to view recorded data on the currently connected USB stick.

R1: A list of all recorded data found on the USB stick is displayed here.
R2: This button opens the recording of the item currently selected in R1.

![system](assets/Bearbeitet/Replay_loaded_bearbeitet.png)

R3: The file name of the currently opened recording is displayed here.
R4: This button closes the currently opened file. **Caution: If the USB stick is removed while a file is open, the USB connection is interrupted and the c-Rio must be restarted to reactivate it!!!**
R5: This marker indicates the starting point of the data displayed in R8.
R6: This is a graph showing the progression of the IFT value in the open file.
R7: Here you can read the information about the recording that is stored in the file. There are two tabs, "System Settings" and "Rules".
R8: Up to 2 seconds of data are displayed here in detail. The starting point of the display is selected using R5 and loaded using R17.

### System Settings Tab

![Recalc](assets/Bearbeitet/Replay_systemsettings_bearbeitet.png)

R9: Here you can read the name and MAC address of the holder used.
R10: Here you can read the start time of the recording.
R11: Here you can read the battery level that existed at the start of the recording.
R12: Here you can read the sensors and reference voltage used in the recording.
R13: Here you can read the k and d factors selected for the 3 channels.
R14: Here you can read the information added to the recordings by the user.

### Rules tab

![Recalc](assets/Bearbeitet/Replay_rules_bearbeitet.png)

R15: Here you can select which rule settings should be read in the R16 data.
R16: The rule settings for the rule selected in R15 are displayed here.
R17: This button can be used to recalculate the IFT values in R8 using the starting point R5, the k and d factors R18, the window length R19 and the channel R20.
R18: New k and d factors for recalculation with R17 can be set here.
R19: Here, a new window width can be selected for recalculating the data with R17.
R20: Here, the channel used for recalculating the IFT values in R8 can be set.

## IFT Value Tab

![IFT_Value_Tab](assets/Bearbeitet/IFT_Value_bearbeitet.png)

This tab displays the current history of the IFT value for the various rules set for an active connection.
V1: Here you can select from which of the rules the thresholds in V2 should be displayed.
V2: Here you can see the history of the IFT values of the rules and the thresholds of the rule set in V1.

## nRT Rule tab

![nRT_Rule_Reiter](assets/Bearbeitet/NTR_Rule_bearbeitet.png)

In this tab, the nRT rules can be read out and, in the case of the "Dashboard" holder selection, also adapted.
N1: The parameters set here can be loaded into the corresponding rules using the N3 buttons.
N2: Here, the settings of the currently active nRT rules can be read out.
N3: When pressed, these buttons load the data from N1 into the corresponding rule in N2.
N4: These buttons can be used to activate the corresponding rules.
N5: These identifiers can be used to identify which nRT rules are currently activated and which rules are currently triggering an "intervention".

## Stability tab

![stability-tab](assets/Bearbeitet/Stability_bearbeitet.png)

In the Stability tab of the dashboard, you can set the parameters for the dashboard holder selection, read the current rules and view a graph of the real-time data for the main rule.

C1: Here you can select the desired control algorithm.
C2: Here you can see the control algorithm currently used by the main rule.
C3: This identifier shows whether data is currently being recorded.
C4: With this slider you can set the time displayed in C7, C8 and C16.
C5: This button can be used to pause graphs C7, C8 and C16 or to restart them.
C6: Here, the control parameters of the main rule can be set and the current parameters can be read out.
C7: This graph shows the real-time data of the IFT value and the set thresholds.
C8: This graph shows the real-time data of the overrides currently controlled by the c-Rio.
C9: This button loads the main rule parameters entered in C6 into the activated parameters.
C10: This button activates and deactivates the main rule for the "Dashboard" connection types.
C11: This button allows you to reset a triggered rule if its algorithm requires a manual reset.
C12: This identifier indicates whether the main rule is currently activated.
C13: This identifier indicates whether the main rule is currently triggering and adapting the overrides.
C14: This identifier indicates whether data is currently being recorded.
C15: These identifiers indicate which nRT rules are currently activated and which are triggering. The inner circle is coloured when the rule is activated and the outer ring is coloured when the rule intervenes.

![Header](assets/Bearbeitet/nRT-Indikator-bearbeitet.png)

C16: This graph shows the timeline of the activation and intervention of the main rule.

### Parameters

Depending on which mode is set active, different parameters can be changed. To change these parameters to new values, press the "update" button on the bottom. An exception is the window length in watch mode. It can always be changed.

![parameter](assets/Bearbeitet/parameter.png)

#### Window length 			  			

{ms} window length

This parameter changes the time window for the calculation of the IFT-Value. The larger the window, the more sluggish the system reacts to changes. For example, a single spike in the process is weighted less on the IFT-Value calculation in a larger window. In “Watch” mode this parameter can be adjusted live. In all other modes, this can only be done using the "update" button as mentioned before.

#### Minimum IFT Level

{-} ift value level

This parameter is the minimum used value for the rule. All values below this will be ignored. For example is this needed if you use the filter options and scale it to the unfiltered values. When you move quick with the tool inside the machine there could be high frequency parts in the signal and set the system to interfere. So you can use this value to get the system not interfering while it is only moving.

#### Stability_Channel 		  			

{-} channels

If you have a three channel holder you can change the channel which is used to calculate the IFT value with this drop down menu. You can use any of the three channels or multiple channels at once. If you use a one channel holder this parameter will be ignored and the IFT value calculated with the one available channel.

#### Upper threshold 		

{-} upper threshold

If the IFT value exceeds the threshold, the overrides are set to the defined values by the SPU. The bigger this value, the more “instable” the process is allowed to become, before override adaptions are activated.

#### Lower threshold 			  			

{-} lower threshold

If the IFT-value falls below the lower threshold, the override values will start rising up towards 100% again, following a defined ramp. The lower this value, the more “stable” the process has to become for the overrides to be reset.

#### Ramp 				

{%/ms} ramp

This parameter changes the speed of the override reset. The overrides are not reset instantly, as they follow a ramp to change back to 100%. The bigger this value, the steeper the ramp and the faster the system goes back to 100% spindle speed and feed rate.

A value of e.g. 0.01 %/ms would increase the feed rate and/or spindle speed to 10 % within 1 second.

#### Feed override 			

{0-100%} Setpoint for feed rate

This parameter is used in the modes "Stop", “Stability reduction”, “Stability 2 Level” and “Direct output”. In "Stop", “Stability 2 Level” and “Direct output” this value defines the override applied to the machine tool control system, the moment the ICOtronic system activates the feed rate adaption of the machine.
In "Stability reduction" this value defines the minimal feed rate override, which is sent to the machine by the ICOtronic system. The reduction cannot fall below this value.

#### Spindle override 		  			

{0-100%} Setpoint for spindle speed

This parameter is used in "Stop", “Stability reduction”, “Stability 2 Level” and “Direct output”. In “Stability 2 Level” and “Direct output” this value defines the override applied to the machine tool control system, the moment the ICOtronic system activates the spindle speed reduction of the machine.
In "Stability reduction" this value defines the minimal feed rate override, which is sent to the machine by the ICOtronic system. The reduction cannot fall below this value.

#### Feed reduction factor 					

{0-100%} Reduction factor

This parameter is used in the “Stability reduction” mode. This value controls the intensity of the reduction steps of the feed rate.

As an example: A value of 5 % for "Feed reduction factor" results in continuous reduction of 5% of the override as long as the IFT-Value is bigger than the upper threshold at each calculation interval.

Reduction step 1: Reduction from 100 % to 95 %
Reduction step 2: Reduction from 95 % to 90 %
…and so on.

#### Spindle reduction factor 				

{0-100%} Reduction factor

This parameter is used in the “Stability reduction” mode. This value controls the intensity of the reduction steps of the spindle speed.

As an example: A value of 5 % for "Spindle reduction factor" results in continuous reduction of 5% of the override as long as the IFT-Value is bigger than the upper threshold at each calculation interval.

Reduction step 1: Reduction from 100 % to 95 %
Reduction step 2: Reduction from 95 % to 90 %
…and so on.

#### Deadtime 					

{ms} deadtime

This parameter is only used in the “Stability reduction” mode. This value equals the time in ms the system pauses before checking if it should reduce the spindle speed and feed rate again. The smaller this value, the quicker the ICOtronic system reduces the speed. As a reference value for first tests 300 ms can be mentioned. This means, each 300 ms feed rate and/or spindle speed are adapted as long as the IFT value exceeds the threshold.

**Examples**:

In the pictures below, there are 2 different Deadtimes set. The first picture has a shorter Deadtime than the second one. It can be seen that the minimal Overrides are reached quicker with a lower Deadtime.

Feed reduction factor: 5%; Feed override min: 40%; Spindle reduction factor: 7%; Spindle override min: 10%

Deadtime: 100ms

![deadtime1](assets/deadtime1.png)

Deadtime: 300ms

![deadtime2](assets/deadtime2.png)

#### Low-Pass Filter

{Hz} cutoff frequency
{-} active/inactive

This parameter is used as low pass filter cutoff frequency when calculating the IFT values. The text-field is used to give the cutoff frequency and the circle is a button to activate the low-pass filter. The button will turn blue if the filter is set to active.

#### High-Pass Filter

{Hz} cutoff frequency
{-} active/inactive

This parameter is used as high-pass filter cutoff frequency when calculating the IFT values. The text-field is used to give the cutoff frequency and the circle is a button to activate the high-pass filter. The button will turn blue if the filter is set to active.

#### Scale to unfiltered

{-} active/inactive

This circle shaped button shines blue if activated. The filtered (high-pass and low-pass filtered) signal will be set in relation to the unfiltered signal if the function is activated. Following the activation the IFT value can be at maximum a "1". **If the low-pass AND high-pass filters are deactivated the signal will always be a "1".**

### Modes 					

The modes are:

![modes](assets/Bearbeitet/modes.png)

#### WATCH 				

The STH and the STU are connected in this mode. Moreover, the IFT-Value will be evaluated in order to watch the signal generated in cutting processes. However, this mode is not a control mode and thus not taking any actions in the machine control system. This mode is also suitable for testing the connection between STH and STU. In this mode, the “IFT value factor” and “IFT value offset” can be changed. Furthermore, this is the only mode where you can instantly change the "Window length" without having to use the "update" button.

#### STABILITY 2 LEVEL 			  			

This is one of the two modes which can be used to control the machining process. In this mode, the parameters used are the “Upper threshold”, “Lower threshold”, “Ramp”, “Feed override” and “Spindle override”. If the IFT value exceeds the “Upper threshold”, the system will directly set the overrides to the values of “Feed override” and “Spindle override” defined in the Dashboard. If the IFT value reduces and falls below the “Lower threshold”, the system will start to increase Spindle speed and Feed rate back to 100% in form of a ramp. The speed of this increase is defined by the “Ramp” parameter.

#### STABILITY REDUCTION 				  			

This is one of the two modes which can be used to control the machining process. In this mode, the parameters used are the “Upper threshold”, “Lower threshold”, “Ramp”, “Feed override min”, “Feed reduction factor”, “Spindle override min”, “Spindle reduction factor” and “Deadtime”. If the IFT value exceeds the “Upper threshold”, the system will reduce spindle speed and feed rate. The factors of how much they are reduced are the two “override" factors. After a reduction step, the system waits the “Deadtime” to see if the IFT value is still above the “Upper threshold”. If it is still above, the system will reduce the overrides again. If the “override min” values are reached, the system will no longer reduce the spindle speed and feed rate. If the IFT-Value falls below the “Upper threshold”, the system holds the active overrides applied by the SPU. If the IFT-Value sinks below the “Lower threshold”, the system starts to increase spindle speed and feed rate. The speed of this increase is defined by the “Ramp” parameter.

#### DIRECT OUTPUT 					  			

This mode is primary used while installing the system. Beside the “IFT value factor” and the “IFT value offset”, the “Feed override” and “Spindle override” can be changed. The values given for the overrides will be directly sent to the output, independent from the IFT-Value. Therefore, a specific spindle speed or feed rate can be applied without any sensor-input or activation signal from the machine-control-system (M-command). This mode should be used to check if the connection between the SPU and the machine-control-system is working as designed. 

#### STOP 					  			

This mode works nearly identical to "stability 2 level" mode. The only difference is that the system doesn't use the "lower threshold". If the system changed the overrides these overrides will stay active until ether the digital input of rule enable is reset to "0" or the "Reset Regler" button was pressed.

#### FROM nRT1

This mode uses the settings of the nRT1 rule instead of the main rule to control the overrides.

## Example use-case 			  			

Open the Remote Control Panel and connect to the Dashboard. After the page is loaded, go to the “System” tab and wait for the holder inside the machine to be listed. Now press “Connect” and go to the “Stability” tab. The STH's LED should start blinking and the STU's LEDs in the corners should stop blinking and instead shine continuously. After a short moment, the IFT-Value graph should start to display values different from zero. Change the mode to “Watch” and choose a “Window length” with about 70 ms as a first orientation. Change the “Graph History” to a desired time window. Now, perform a cut in this watch mode with deactivated adaptive control and examine the IFT-Value. In order to take look at the whole process, press the “pause graph” button after the process. Remember that the seconds below the graphs show how many seconds in the past this point was. The following figure represents an example cut in the watch mode.

![example](assets/example.png)

Now change to on of the two control modes and set the parameters of the “Upper threshold” and “Lower threshold” to plausible values, for the in-process parameter adaption. Repeat the cut, in which the override adaption is now activated.

![example2](assets/example2.png)


Look if the parameters are chosen appropriately in order to control the process. If not, change them in an adequate way.

The time required to optimize the system for the use case varies. This depends on the intensity of chatter, the process time, the experience for configuring the Dashboard and the experience of the machine operator.

# How to use the OPC UA-Server of the SPU

## Connecting the OPC UA-Server

First, an OPC UA client is required on your PC. For example use the UaExpert client UaExpert v1.5.1. A user account is required.
Download link: https://www.unified-automation.com/downloads/opc-ua-clients.html  
Afterwards open the UaExpert client-program. When the program is open you have to click on “Server” at the top menu and then on “Add…”. This opens a window to search for and connect with the OPC UA-Server of the Signal Processing Unit (SPU) of the ICOtronic system.

 ![find_server](assets/find_server.png)

In the new window you have to go to the menu entry “Custom Discovery” and double click the sub menu entry „< Double click to Add Server… >“. Now a new window will open. Here you have to input the address which you can find in the dashboard of the SPU:

![opcua-adress](assets/opcua.png)

Now the server should be found and you can open some sub menu entries. Double click the “None – None (uatcp-uasc-uabinary)”. Now the “OK” button should be usable and you can click it to exit this window.

![add_server](assets/add_server.png)

After that, the server should be visible on the left side of the menu. Now you have to right-click the server and then click on “Connect”.

 ![connect_server-server](assets/connect_server.png)

## Visualisation of the variables

After connecting to the OPC UA-Server you should be able to see variables on the left side of the menu.

 ![variables_opcua](assets/variables_opcua.png)

The variables can be sorted into 3 groups: "command", "data" and "param".
In the "command" group you can find bool variables which activate a command if set to "true". An example would be that setting the variable "disconnectHolder" to "true" the system will disconnect the momentary connected holder.
The "data" group contains values which are calculated/set by the system. An example would be that you can find the momentary IFT-value in the variable "iftValue".
The "param" group can be split into 2 subgroups. The "active" subgroup contains the momentary set parameters of the rule engine. The "set" subgroup can be used to change the parameters of the rule engine.

With a double click, these variables can be opened and shown on the upper right-hand side of the menu.

 ![note_details](assets/note_details.jpg)

In this window, it is possible to read the different value parameters of the chosen element. For example, the actual value of the element or the timestamp of the last time, this element was updated. The menu item “Value” shows the last read value of this element.
In order to show an element permanently in the middle tab of the screen, you can drag&drop it from the bottom left into the big tab in the middle. Alternatively you can right click in the big middle tab. Now a menu should open and you have to click on „Add custom node…“.

![add_note](assets/add_note.png)

After that, you have to state the variable name of the element you want to show. Every element of the OPC UA-Server can be chosen via its identifier. If an element is selected, the identifier can be read out at the element parameters in the right upper tab. There, you can pick the entry “NodeId” and find the required information.

![note_id](assets/note_id.jpg)

After inputting the NodeId you can press the “OK” button. Now the chosen element should be shown in the middle part of the program. It is possible to show more than one element in the middle of the screen by repeating this process.

![note_main_window](assets/note_main_window.png)

## Changing of variables

To change variables, for example the "windowLength" you have to choose the corresponding variable in the "set" subgroup of the "param" group. Now you can change the "Value" of this variable. If you look at the "active" parameter of the variable you will notice that the value wasn't changed automatically.

![note_value_change](assets/note_value_change.png)

The value will only be written into the active parameter after the "setStabilityParam" parameter of the "command" group has been written "true". Afterwards you can see that the active parameter was written with the set value.
Note that the "setStabilityParam" command changes all changed parameters at once.

![note_changed](assets/note_changed.png)

## Recording of variables

With UaExpert you can also save the variables into a ".csv" file. To use this function you have to go to "Documents -> Add Document" and in the following window you have to choose "Data Logger View".

![add_data_logger](assets/add_data_logger.png)

The "Data Logger View" will open.

![data_logger](assets/data_logger.png)

Now you can add the variables just like you did in the "Data Access View" window before. On the right side you can edit various parameters for the recording of the variables.

![logger_variables](assets/logger_variables.png)

Below the chosen variables you can find the parameters of the recorded files. There you can define the data path for the recording, the maximum number of lines written into the file and how many files from the past should be kept before overwriting the files.

![logger_output_details](assets/logger_output_details.png)

**ATTENTION:** If a new recording is started the old recordings get a number at the end of the name and will get an increment of this number thereafter. Therefor you have to be careful when recording so that later you still know which file was which recording.

![logger_output_files](assets/logger_output_files.png)

At the bottom of the Data Logger View you find the "Start" and "Stop" button and an information about how many values were written in the momentary recording.

![logger_runtime](assets/logger_runtime.png)