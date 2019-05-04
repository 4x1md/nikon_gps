# Development tests of DIY GPS for Nikon DSLR

## Test equipment

1. Siglent SDS1204X-E oscilloscope
2. GOPHET CPS-3205 II power supply
3. UNI-T UT61E DMM
4. Siglent SDG1032X signal generator

## Tested Circuit
![DUT](../images/tested_circuit.png)


## Tests without the GPS module
The GPS module is hard to manually solder and especially desolder. Thus, before assembling it, I wanted to make sure that the circuit works as expected.

### Power-on

![Power-on without GPS](../images/development_tests/SDS00006.png)

Channel  | Signal
--- | ---
**CH1:** | 5V
**CH2:** | 3.3V_EN (U4.3)
**CH3:** | 3.3V
**CH4:** | GPS_OUT

### Power-off

![Power-on without GPS](../images/development_tests/SDS00008.png)

Channel  | Signal
--- | ---
**CH1:** | 5V
**CH2:** | 3.3V_EN (U4.3)
**CH3:** | 3.3V
**CH4:** | GPS_OUT

### On/off button

**Turning 3.3V on**

![Power-on without GPS](../images/development_tests/SDS00012.png)

Channel  | Signal
--- | ---
**CH2:** | ON_SW (U3.1)
**CH3:** | 3.3V_EN (U4.3)
**CH4:** | 3.3V

**Turning 3.3V off**

![Power-on without GPS](../images/development_tests/SDS00016.png)

Channel  | Signal
--- | ---
**CH2:** | ON_SW (U3.1)
**CH3:** | 3.3V_EN (U4.3)
**CH4:** | 3.3V

### Logic level shifting

Logic level shifting was tested by injecting pulses to the input of U2. Pulse frequency was 2400Hz and amplitude 3.3V.

**Rise time**

![Power-on without GPS](../images/development_tests/SDS00020.png)

**Fall time**

![Power-on without GPS](../images/development_tests/SDS00022.png)

**Output pulses with 3.3V input**

![Power-on without GPS](../images/development_tests/SDS00025.png)

**Output pulses with 2.6V input**

One more issue I tried to test is response of the level shifting IC to LOW=0.4V and HIGH=2.475V pulses. The values were taken from the datasheet of the GPS module. Later, tests with GPS module assembled demonstrated that these pulses don't emulate the real-world voltage levels.

![Power-on without GPS](../images/development_tests/SDS00028.png)

Channel  | Signal
--- | ---
**CH1:** | GPS_TX (C2)
**CH4:** | GPS_OUT


## Tests with the GPS module

The same tests were performed with the GPS module assembled.

### Power-on

![Power-on without GPS](../images/development_tests/SDS00032.png)

Channel  | Signal
--- | ---
**CH1:** | 5V
**CH2:** | 3.3V_EN (U4.3)
**CH3:** | 3.3V
**CH4:** | GPS_OUT

### Power-off

The pulses on the GPS_OUT line are UART transmissions of the GPS module.

![Power-on without GPS](../images/development_tests/SDS00057.png)

![Power-on without GPS](../images/development_tests/SDS00058.png)

Channel  | Signal
--- | ---
**CH1:** | 5V
**CH2:** | 3.3V_EN (U4.3)
**CH3:** | 3.3V
**CH4:** | GPS_OUT

### On/off button

**Turning 3.3V on**

![Power-on without GPS](../images/development_tests/SDS00038.png)

Channel  | Signal
--- | ---
**CH2:** | ON_SW (U3.1)
**CH3:** | 3.3V_EN (U4.3)
**CH4:** | 3.3V

**Turning 3.3V off**

![Power-on without GPS](../images/development_tests/SDS00040.png)

Channel  | Signal
--- | ---
**CH2:** | ON_SW (U3.1)
**CH3:** | 3.3V_EN (U4.3)
**CH4:** | 3.3V

### Logic level shifting

**Rise time**

![Power-on without GPS](../images/development_tests/SDS00041.png)

**Fall time**

![Power-on without GPS](../images/development_tests/SDS00042.png)

**Output pulses with 3.3V input**

![Power-on without GPS](../images/development_tests/SDS00043.png)

Channel  | Signal
--- | ---
**CH1:** | GPS_TX (C2)
**CH4:** | GPS_OUT

This test shows that the real logic levels of the ORG1410-PM04 UART is 1.8V. According to the SN74LV1T126DBVR datasheet, it is not supposed to work with 1.8V input when powered with 5.0V. However, this test shows that it works well.

### UART waveforms

![Power-on without GPS](../images/development_tests/SDS00045.png)

![Power-on without GPS](../images/development_tests/SDS00051.png)

--- | ---
**CH1:** | GPS_TX (C2)
**CH4:** | GPS_OUT
