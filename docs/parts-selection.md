# Parts choice for DIY GPS for Nikon DSLR
Parts which I considered while working on this project.

## GPS modules:

1. Maestro A2235-H

	Symbol and footprint: https://www.snapeda.com/parts/A2235-H/Maestro%20Wireless/view-part/

2. Hornet ORG1411-PM04

	Datasheet: https://origingps.com/products/hornet-org1411/

	Where to buy: https://vuec.co.uk/SEMICONDUCTORS/COMMUNICATION_MODULES/GSM_GPS_GPRS_HSPA_EDGE_LTE_MODULES/ORG1411_PM04_Module_GPS_I2C_SPI_UART_40_85_C_10x10x3_8mm_SMD_2_5_5V_1130_0.html

	3D model: https://grabcad.com/library/origin-gps-org1510-1

3. ORG1410-PM04

	Datasheet: https://origingps.com/products/hornet-org1410/

4. MT3339:

	https://www.instructables.com/id/Change-Baudrate-of-MT3339-PA6C-With-Arduino/

	https://www.pololu.com/product/2138/resources

## Level converters:

1. TI SN74LV1T126DBVR (Level converter, tri-state output, Output Enable)
2. Nexperia 74LV1T126GWH (Level converter, tri-state output, Output Enable, SC-70-5)
3. Nexperia 74LV1T126GVH (Level converter, tri-state output, Output Enable, SOT-23-5)
4. TI SN74LV1T34DBV (Level converter, no Output Enable pin)
5. SN74LVC1T45
6. MAX3370
7. MAX3371

## AND gates with voltage level translation

1. Nexperia
* 74LV1T08
* 74AUP1T08

2. TI
* SN74LV1T08
* SN74AUP1T08

3. ON SEMI
* MC74VHC1GT08

AUP series have Schmitt trigger inputs.

## Schmitt triggers for ON/OFF button debouncing

1. Texas Instruments SN74LVC1G14DBVR
2. Nexperia 74LVC1G14GW,125
3. Diodes Incorporated 74LVC1G14SE-7

## Diode

Low Vf Schottky diode is requred.

SOD-523

1. ON Semiconductor NSR0340V2T1G
2. ST BAS40-02V-V-G SOD-523
3. ON Semiconductor RB521S30T5G - selected diode

SOD-323

1. ON Semiconductor NSR0170HT1G SOD-323
2. ON Semiconductor NSR0240HT1G SOD-323
3. Toshiba CUS521,H3F SOD-323 - lowest Vf

## ON/OFF switch driver

1. MAX16054
https://datasheets.maximintegrated.com/en/ds/MAX16054.pdf
https://www.mouser.co.il/ProductDetail/MAX16054AZT%2bT

2. LTC2951-1/LTC2951-2
http://www.analog.com/media/en/technical-documentation/data-sheets/295112fb.pdf

3. 6x6x11mm or 6x6x12mm button.

https://www.aliexpress.com/item//32859870553.html

4. LTC6994-2

## Cable from GPS to camera

1. https://www.ebay.com/itm/Micnova-GPS-N-7-Camera-GPS-cable-for-Nikon-D3300-D3200-D5300-D7100-D7000-D610/271632524840

## Power supply

1. Analog Devices ADP2108AUJZ-3.3-R7 - buck converter, high efficiency on low currents, SOT-23-5
2. TI TPS62203DBVR - SOT-23-5
3. TPS62840 - VSON-8 - more difficult to solder
