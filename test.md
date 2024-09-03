# Table of Contents

- [1. FCB Manual operations](#1-fcb-manual-operations)
- [2. FCB Supported models](#2-fcb-supported-models)
- [3. FCB Supported Miner Management Software](#3-fcb-supported-miner-management-software)
- [4. LED Indications](#4-led-indications)

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
-----------------------------------------------------------------------------------------------------------------------------

# 2. FCB Supported models

|Model Variant     |Hashboard model                |Chip Type|No of ASICS|
|------------------|-------------------------------|---------|-----------|
|S19               |BHB42831                       |BM1362   |88         |
|S19 with 126 Asics|                             |BM1362   |126        |
|S19 JPRO          |BHB42601*, BHB42621 BHB42641*  |BM1362   |126        |
|S19 JPRO (noPIC)  |BHB42603*, BHB42631*, BHB42651*|BM1362   |126        |
|S19 KPRO          |BHB56902, BHB56903*            |BM1366   |77         |
|S19 XP            |BHB56801, BHB56802*            |BM1366   |110        |

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
