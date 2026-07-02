
# Retro-VFO-With-OCXO-RTC-IQ-Balance - 100kHz to 30MHz
ESP32 Digital VFO, Rotation Dial covering 100kHz to 30MHz, Oven Controled Xtal Oscilator (OCXO) and Real Time Clock (RTC)

While some of the parts used are specialized, none are expensive.

  AC9NM Updated as of June 2026:
  Board manager: esp32 ver. 3.3.10
  Arduino IDE 2.3.10
  Board: DOIT ESP32 Devkit V1 Module (30-pin) or NodeMCU-32S (30-pin)
  Library: LovyanGFX ver. 1.2.24
  Kicad 10.x PCB Layout & Gerbers
  KY040 Rotary Encoder
  ST7789 IPS 1,9" display 170x320 and 0.91 inch OLED for clock
  CTI OSC5A2B02 10 MHz Oven Controled Xtal Oscillator (OCXO)
  Si5351A Clock generator IC (TSSOP-8)
  74LVC1G04DBVR single inverter gate (SOT23-5 package)
  ICS511 or ICS501 frequency multiplier IC (SOIC-8)
  DS3231N Real Time Clock (RTC) module

  Note: Make sure that lines 38 and 39 in si5351.h file has the correct address for your Si5351A
  and crystal frequency.
  
  All outputs are at the same frequency. CLK2 can be enabled/disabled with setting carON on line 161.
  Quadrature outputs are on CLK0 and CLK1. CLK0 leads CLK1.
  The Si5351A CLK2 is inverted in relation to CLK0 for frequencies 3.2MHz or higher. 
  The Si5351A CLK2 is inverted in relation to CLK1 for frequencies below 3.2MHz. 

  Since the Si5351A's outputs are buffered, setting the Si5351 drive levels has no effect on the
  buffered outputs levels.
  
  The DS3231N Real Time Clock module (RTC) is set by a NTP server over WiFi. Therefore, the module does
  not need a battery. The WiFi is turned off after the time is set but you can just leave it on 
  if you wish by commenting out lines 566-568. Set up your ssid and password on lines 99 and 100. 
  The RTC uses I2C addresses 0x57 and 0x68. NTP Client Setup for UTC is on line 10.
  If you don't install the RTC, the time is simply not displayed.

  The DACs are connected to a JST jack so that they can be used with Tayloe type QSE/QSDs for I/Q Balance,
  0 - 3.2V output.

  Partial CAT Control Kenwood ST-2000 Emulation, 9600 BAUD, by Barb (Barbaros ASUROGLU) - WB2CBA.

 <img width="1023" height="575" alt="ST7789_170x320" src="https://github.com/user-attachments/assets/6d389618-2c05-42be-9828-61553c783b7a" />
  1.9 inch IPS ST7789 170x320 LCD
 <img width="1023" height="575" alt="ST7789_240x320" src="https://github.com/user-attachments/assets/2cd4b891-fec1-465f-b938-919701b32308" />
  2.8 inch IPS ST7798 240x320 LCD
__
