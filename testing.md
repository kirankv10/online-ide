# Controller Board Operation Manual Ver 1.0

## Table of Conetents 

* [1. FCB Manual operations](#1-fcb-manual-operations)
* [2. FCB Supported models](#2-fcb-supported-models)
* [3. FCB Supported Miner Management Software](#3-fcb-supported-miner-management-software)
* [4. LED Indications](#4-LED-Indications)
* [5. Foundry Dashboard](#5-Foundry-Dashboard)
* [5.1 Mining modes](#51-Mining-modes)
* [5.2 Temperature and Fan Control](#52-Temperature-and-Fan-Control)
* [5.3 Hashboard Selection](#53-Hashboard-Selection)
* [6. Troubleshooting with the help of detailed logs](#6-Troubleshooting-with-the-help-of-detailed-logs)
* [7. Remote firmware Update](#7-Remote-firmware-Update	)
* [8. Firmware Auto Update](#8-Firmware-Auto-Update)
* [9.Reset Password](#9-Reset-Password)
* [10. Network Settings](#10-Network-Settings)
* [11. Advance Settings](#11-Advance-Settings)
* [12. Throttle Mode](#12-Throttle-Mode)
* [13. Control Board Swapping](#13-Control-Board-Swapping)
* [14. Autotune Test Results](#14-Autotune-Test-Results)
* [15. Error Messages on DASHBOARD](#15-Error-Messages-on-DASHBOARD)
* [16. Additional Document links](#16-Additional-Document-links)
* [17. FAQ’s](#17-FAQs)


# 1. FCB Manual operations 
This guide can be used to understand the working operation and features of the Foundry Control Board.

### Key Features:
* Supports Immersion mode
* Overclocking and underclocking support
* Custom Firmware (NOT dependent on cgminer). Supports cgminer API’s.
* Both High Power and Low power fans are supported.
* Mismatch of HASHBOARDS is permitted using the Foundry Control Board. Users can swap the faulty HASHBOARD with a healthy board from a different miner of the same variant and start mining without any hassle. This feature is not supported in the stock miner/control board.


***Below Fig shows the CB Overview***

![1](https://github.com/user-attachments/assets/af86e0ef-02ad-4b53-9b86-700e7473f0b6)


* **Dual-core Arm Cortex-A7 650 MHz processor** <br>
* **4 Gb / 512 MB RAM** <br>
* **4 GB internal memory** <br>
--------------------------------------------------------------------------------------------------------------------------

# 2. FCB Supported models
|Model Variant     |Hashboard model               |Chip Type|No of ASICS|
|------------------|------------------------------|---------|-----------|
|S19               |BHB42831 BHB42801             |BM1362   |88         |
|S19 with 126 Asics|BHB42841                      |BM1362   |126        |
|S19 JPRO          |BHB42601, BHB42621 BHB42641*  |BM1362   |126        |
|S19 JPRO (noPIC)  |BHB42603*, BHB42631, BHB42651*|BM1362   |126        |
|S19 KPRO          |BHB56902, BHB56903*           |BM1366   |77         |
|S19 XP            |BHB56801, BHB56802*           |BM1366   |110        |
--------------------------------------------------------------------------

> [!NOTE] 
> Hashboard models with ‘*’ model is not tested. But from the research done on the web, those     models have the same number of ASIC’s and the same chip type as the tested model.<br>
> Not aware of the exact model on which the S19 JPRO(noPIC) tests have been run.


# 3. FCB Supported Miner Management Software
* Optifleet    [compatibility level – complete]
* Foreman    [compatibility level – intermediate]
* BTCtools     [compatibility level – complete]

# 4. LED Indications
* As soon as the board is powered ON. GREEN LED starts glowing.
* After 15-20 seconds the RED LED starts blinking. Indicating that the firmware has started.
* RED LED stops blinking as soon as the initialisation is done and the mining operation starts. GREEN LED shall stay solid.
* Upon executing the locate operation, the RED LED begins to blink rapidly. GREEN LED will remain solid.
* Both the GREEN LED and RED LEDs will be solid in the event of an error.
* The LED indications are mentioned for firmware version 2.4.3

***Below table shows LED INDICATION for firmware version 2.4.3***

![2](https://github.com/user-attachments/assets/0f219255-7b15-4774-a7ee-6f1f61499026)


# 5. Foundry Dashboard
* The username and password are initially requested while accessing the dashboard.<br>

***Below fig shows the Login access popup to the dashboard***

![3](https://github.com/user-attachments/assets/ad532983-d72a-44f2-9fea-4de0e287b829)


* By default, the username and password for all the miners is : 
* Username: <b> root </b>
* Password: <b> root </b>
* On fresh-installation: After accessing the dashboard, the miner model will be unknown initially. Wait for a 5 min duration for the miner model to be auto-detected.<br>

<br>

***Fig illustrates the dashboard of the miner while the control board is powered ON for the first time.***

![4](https://github.com/user-attachments/assets/4c712626-e26b-4553-adbf-79cb437214d4)
<br>

* The dashboard looks like above after the miner model is auto-detected. 
* This will happen only if the miner-model is supported.

***Below fig shows Miner Dashboard during mining***

![5](https://github.com/user-attachments/assets/938e33c8-c8b9-4d6b-9785-c3d51306fb91)
<br>

# 5.1 Mining modes
* Auto-tuning of the miners. Overclocking and underclocking operation of the miners can be achieved using this section.
* The user has the privilege to run the miner in three modes: <b> AUTO </b> ,<b> FIXED</b>  & <b> SLEEP</b> .
*  <b> Auto mode </b>, there is an option to select a work mode i.e.,
* <b> Normal mode </b>, the miner runs with the stock hashrate in this mode.
* <b> Advanced mode </b>, where the user can  set his own target hashrate.
* <b> Low energy mode </b>, which generates a lower hashrate by consuming less power and providing better efficiency.
* <b> High power mode </b>, which generates higher hashrate by using some extra power.<br>
 <b> Fixed mode </b>, the user can set frequency and voltage of their choice at which the miner has to perform.
* <b>Sleep mode </b>  puts the miner to sleep and will be useful for curtailment of the miners. Fans will be running at full speed if they are available. Hashboards and the PSU will be turned OFF. 

***Mining Modes available under Auto Mode***

![hb before ](https://github.com/user-attachments/assets/f5eaaa95-8a57-47ad-9a95-a714607784d5)



***Fixed mining mode with frequency and voltage setting***

![hb after ](https://github.com/user-attachments/assets/d91d938a-7fdb-4b65-ba4d-f56dbb0061eb)

***This flow chart shows the Different Miner modes available for mining under the Foundry Firmware***

![image](https://github.com/user-attachments/assets/cd176811-dba4-4082-aee2-5b0fa13b34b0)

# 5.2 Temperature and Fan Control
* The fan speed and recommended chip temperature can be easily adjusted by the user.
* There are three options for fan control:<br>
<b>Auto (Air-Cooled):</b> This mode allows the user to configure the desired chip temperature at which the ASIC chips should operate, as well as the critical threshold temperature at which the chips should shut down.
Fans will adjust their speed based on the temperature accordingly.<br>
<b>Manual mode:</b> The user can specify the critical temperature at which the fan should stop working and adjust the fan speed between 0 and 100% to suit their needs.<br>
<b>Immersion mode:</b> The fans do get disabled and will be helpful in the miner immersion. User should set the critical temperature at which the miner should shut down.

***Below fig shows Different modes of fan control***

![6](https://github.com/user-attachments/assets/13c0a3b1-b109-4e07-8161-3f82208094db)


![7](https://github.com/user-attachments/assets/f5d33205-4552-4c12-a41c-81b15825189c)


![8](https://github.com/user-attachments/assets/f6351571-3848-4d2e-b49c-41805f0b4dd1)


# 5.3 Hashboard Selection
* By disabling the hashboards that are not required/not healthy, the user can choose to operate the miner with healthy hashboards.
* The user may choose which combination of hashboards to use for mining, as an alternative to employing all three.
* This will be helpful when one or 2 hashboards are not performing well or if they are faulty and have gone for repair. Instead of having the miner in idle state, users can disable the disconnected hashboards and continue to mine with the working ones.

***Below fig showsHashboard enable/disable feature on the dashboard***

![9](https://github.com/user-attachments/assets/5539778e-1dd5-4577-8224-c4daea1d927e)


# 6. Troubleshooting with the help of detailed logs
* The miner's whole set of detailed logs are dynamically available in real time.
* The user can easily download all of the different logs and troubleshoot any issues that may have arisen by using the download option.

***Below fig shows Dynamic logs available at the dashboard***

![10](https://github.com/user-attachments/assets/aa955735-1f19-43e2-86e8-68ec70a112f6)


***Below fig shows Logs available for download***

![11](https://github.com/user-attachments/assets/defb99bf-b942-4d7a-8cac-800254224244)


# 7. Remote firmware Update
* User can update the firmware remotely from the dashboard

***Below fig shows Firmware update page***

![image](https://github.com/user-attachments/assets/12f19fea-8bbe-4f21-95a2-aaf793e2e721)



# 8. Firmware Auto Update
* In the default settings, Auto update feature will be OFF.
* Users have the provision to upgrade to the latest firmware without manually uploading any file by themself.

***Below fig shows Auto Update feature in the Settings page***

![AutoUpdate](https://github.com/user-attachments/assets/21102b48-56bf-402e-8f57-02e3cbe5d029)

# 9. Reset Password
* By default, the username and password for all the miners is : <br>
Username: <b> root </b> <br>
Password: <b> root </b> <br>
* Users can set their own custom password by using the reset password option.

***Below fig shows  Reset password feature in  the Settings page***
![reset password](https://github.com/user-attachments/assets/cd2bbcd1-ea38-4f53-b903-e6a252f279fe)


* New UserName should be entered if the user wishes to change the username. If it is not filled while changing the password, the default username - <b>root </b> remains as it is. <br>
* Enter the current password and then the new password,confirm password. After entering the details press the Update credential button.<br>

# 10. Network Settings
* Network settings are available in the Settings page.<br>
* By default the DHCP settings will be ON.<br>
* The user should disable the DHCP toggle if they require a static IP address for their operation. <br> After accurately filling out each field with the necessary information, click the Apply button.<br>

***Below fig shows Network Settings***
![NetworkSettings](https://github.com/user-attachments/assets/5ebdeb8a-e15b-4372-ba3b-90d1fa5ac7b4)


# 11. Advance Settings
* Under the Advance Settings we do have three sub categories present.<br>
* <b> Restart Mining if Hashrate is lower(%) : </b> </br>
- The percentage in numbers below which the expected hashrate value is not considerable can be entered by the user. The system restarts when the value falls below that threshold. Users can also set the max restart attempts at which the miner should restart when the required hashrate is not generated.<br>
- The default values are:<br>
               - Restart Mining if Hashrate is lower than  –  20%<br>
			   - Max Restart attempts  –  5 <br>
- If the miner is not able to generate the expected hashrate even after the restart attempts are given, then the miner is put to sleep mode.</p>

***Below fig shows Restart Mining feature when the expected hashrate is not reached***
![image](https://github.com/user-attachments/assets/4e4c8d9a-536c-430e-9c23-5ebf7e8e9612)


* <b> Maximum Error Restart : </b>
- The user has the option to define a maximum number of miner restarts.
- The miner will attempt to restart if the same error occurs repeatedly up until the user-specified number of restarts. 
- The default value for the maximum error restart is 5.


***Below fig shows  Maximum Error Restart Feature***
![maaxerrorrestart](https://github.com/user-attachments/assets/925594d0-15fb-47a1-912b-b2b725e69e9b)
![maaxerrorrestart](https://github.com/user-attachments/assets/d1043ad3-3191-453d-9ffd-24af5ff5ec82)


* <b> minimum Required Fans : </b>
- The user can configure the miner to run with the desired number of fans.
- This helps the user to run the miner with less number of fans when a fan fails and the ambient temperature is cool.

***Below fig shows Minimum Required Fans***
![minfans](https://github.com/user-attachments/assets/7714fb91-b400-45b2-84b6-692b8b43a33b)


# 12. Throttle Mode
* The miner enters into a throttle mode when the miner reaches 96% of the critical temperature set.


***Below fig shows Miner entering into Throttle mode in Auto Miner mode***
![throttlemode](https://github.com/user-attachments/assets/2bbc0bc7-ba8a-4616-a50a-4d71b2a3fff1)


The above figure shows the miner entering into the throttle mode when the temperature of the hashboard is more than the critical temperature set in the Auto Miner mode.


***Below fig shows Miner entering into Throttle mode in Fixed Miner mode ***
![image](https://github.com/user-attachments/assets/845eca0e-7944-462e-aae5-daff58e8cd30)

- Above Fig shows the miner entering into the throttle mode when the temperature of the hashboard is more than the critical temperature set in the Fixed Miner mode.
- Miner shall remain in throttle mode till the temperature of the hashboard is reached below 88% of the critical temperature.
- In fixed miner mode, the working frequency is initially decreased by 10% upon activation of throttle mode. Additionally, the miner continues to monitor the temperature and gradually lower the frequency every minute until the temperature drops below 88% of the critical temperature set.
- In Auto miner mode, the target hashrate is initially decreased by 10% upon activation of throttle mode. Additionally, the miner continues to monitor the temperature and gradually lower the target hashrate every minute until the temperature drops below 88% of the critical temperature set.
- The miner tries to generate the best possible hashrate in these conditions given without restarting the miner or putting the miner to sleep.


# 13. Control Board Swapping
* While performing the control board swapping operation from one miner to a different miner, the user needs to reset the control board by selecting the option RESTORE FACTORY SETTINGS that is present in the bottom left in the Settings page.

***Fig Below shows Restore Factory Settings button in the settings page***

![13](https://github.com/user-attachments/assets/624f1d01-0f51-4e43-9843-04f23207f54e)


# 14. Autotune Test Results
Below are the test results of the FCB for the months of May and June benchmarking with the significant competitors
BRAINS , EPIC & OEM.

***S19XP may and june results***

![14](https://github.com/user-attachments/assets/05bceede-1ae0-4b0a-9d9c-554229f82b50)


***S19JPRO may and june results***

![15](https://github.com/user-attachments/assets/ad88d1a0-2399-4937-bd9e-9ad516b97e37)


***S19 may and june results***

![16](https://github.com/user-attachments/assets/e3864c02-f2b4-4c10-84bd-e26da77a899d)


***S19KPRO may and june results***

![17](https://github.com/user-attachments/assets/58e66cca-f4f7-4afd-8def-5f1b2ab0ac77)



# 15. Error Messages on DASHBOARD
* When the Firmware exits from mining conditions or if it doesn’t start mining, the reason for that will be displayed on the Dashboard.
* The name of the error and details regarding those errors is given in the below table  :

---------------------------------------------------------------------------------------------------------------------------------------------------
|Sl No|Error Name                                         |Details                                                                                                                        |Suggested Fixes                                                                                                                                                                    |Extra Info                                                                                                                                                                                                                                                                    |
|-----|---------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|1    |Config File Error                                  |All the Hashboards are disabled in the config File.                                                                            |Enable at least one Hashboard to continue                                                                                                                                          |                                                                                                                                                                                                                                                                              |
|2    |No Pool is Available for Mining                    |Issue Connecting to the Pools through the pool Credentials mentioned in the Config File                                        |Check Internet Connection and Validity of the Pool credentials                                                                                                                     |If the Pool Configuration is modified , issue reboot command to allow the latest Pool COnfiguration to take effect                                                                                                                                                            |
|3    |One or More Fans have Failed                       |Along with the error message you will also get info regarding which fans have been failed                                      |Swap the Fans if this error is being populated continuously                                                                                                                        |By default the Config file will be written to run the miner in Auto(Air-Cooled) Fan mode. If miner is running in immersion mode, change the Fan mode to Immersion in Dashboard’s Settings page                                                                                |
|4    |Temperature Sensors have Failed                    |One or More Hashboard Temperature sensors have failed along with the error information regarding which Sensors have been failed|Check Hashboard Connections                                                                                                                                                        |If you are running the miner with only one or two hashboards, disable the unconnected hashboard in Dashboard Settings page                                                                                                                                                    |
|5    |Detected very Low Ambient Temperature              |One or more Hashboard's Temperature sensor are reading too low ambient temperature                                             |Preheat the Hashboard and issue reboot to continue Mining                                                                                                                          |The Firmware will automatically re-attempt mining after 5 minutes.Issuing reboot multiple times in lower Temperatures might cause damage to the hashboard’s health                                                                                                            |
|6    |Hashboard Serial Port Init Error                   |Indicates the failure of serial port initialisation for one or more hashboards                                                 |Check Hashboard connections and Connectors displayed in the error message                                                                                                          |                                                                                                                                                                                                                                                                              |
|7    |Hashboard Init Fail                                |Incorrect Number of ASICs detected                                                                                             |A simple reboot may solve this error sometimes                                                                                                                                     |If the same issue is encountered even after rebooting try changing the miner model only after making sure about the Miner Configurations. Go to logs and search for the keyword“ASICs Detected” to check which hashboard has the problem                                      |
|8    |Hashboard Init Fail                                |Indicates that the Hashboard is taking too much time to initialize. Hashboard Failed to initialize within Timeout.             |A simple reboot may fix this issue                                                                                                                                                 |                                                                                                                                                                                                                                                                              |
|9    |Unable to Determine Hashboard variant              |Indicates that the Miner variant is not supported by the firmware yet                                                          |Make sure that the miner variant is supported by the firmware and try rebooting once. If the issue still persists, manually select the miner model in the Dashboard’s settings page|This error message also provides you with the details regarding the presence of PIC in the hashboard and the number of ASICs detected                                                                                                                                         |
|10   |Hashboard Mismatch                                 |Indicates that the Miner contains hashboards with different number of ASICs or one of the Hasboards is defective               |A Simple reboot will solve this error most of the times                                                                                                                            |This error will be displayed only during the first run when the Firmware tries to auto-detect the miner model and also if the config file is deleted or corrupt.This error message also provides you with the details regarding the number of ASICs detected in each hashboard|
|11   |Miner is not able to generate the Expected Hashrate|Indicates that the Miner was not able to generate the expected hashrate for the current configuration in the last 2 Minutes    |                                                                                                                                                                                   |This will auto heal sometimes, but if this is happening too often , one of the hashboards might be defective                                                                                                                                                                  |
|12   |Hashboard has reached the Max Allowed Temperature  |Indicates that the Miner has reached the max critical temperature that has been set                                            |                                                                                                                                                                                   |                                                                                                                                                                                                                                                                              |
-------------------------------------------------------------------

#### Some of the example error messages are shown below:


***Hashboard Init Fail***

![hashboard init fail](https://github.com/user-attachments/assets/550143c3-265a-445b-a1e9-da5a6083cfe9)



***No Pool is available for mining***

![no pool is available ](https://github.com/user-attachments/assets/f5e863d7-63fb-4850-bdc7-d064c66264be)


***Hashboard Mismatch***

![hashboard mismatch](https://github.com/user-attachments/assets/293232ef-5150-4941-a393-88225921e364)

# 16. Additional Document links 
* While the Control Board is not powering up, do follow the instructions mentioned in the following document link.
  [V3 CB Troubleshoot Document](V3CBtroubleshoot.md)

# 17. FAQ'S
Q : What is the firmware version that is running on the Control board? <br>
A :The Firmware version is present on the bottom left corner of the dashboard.

Q : Do you have a specific firmware release date?<br>
A : No

Q : How can I figure out the miner's ideal voltage and frequency that needs to be set?<br>
A : Foundry firmware has the option provided for the user to run the miner in their
      choice of frequency and voltage. They can run the stock settings in the fixed
      mode. For the best output results and to get a good efficiency it’s best to use the 
      AUTO miner mode.

Q : How to get the best efficiency for the same miner model with different hashrate
      variants?<br>
A : The firmware initially automatically determines the miner model and selects the
      least advanced miner variant. If the machine is of a higher variant, the user must
      switch to the appropriate variant.
      For example, if the S19 XP with 141Th miner is connected to the FCB. Firmware 
      considers it to be a S19 XP of 134Th. Users can change this in the miner 
      configuration page.

Q: If there is a problem raised in the firmware that I’m not able to debug, whom should
     I contact?<br>
A: The below is the step by step guide to report any issues related to the FCB.

1. Detailed explanation of the issue the user is facing should be mentioned.
2. Miner model, firmware version that is being used.
3. Screenshot or Screen recordings of the issue that is occurring.
4. Time Stamp of the issue.
5. How frequently is it occurring?
6. Logs: The logs should be downloaded within 1 or  2 days after the issue is
    noticed.
    The user should download and send all the available logs in the FCB 
    (Mandatory).
    The logs should be zipped or compressed in .zip or .tar.gz format.
