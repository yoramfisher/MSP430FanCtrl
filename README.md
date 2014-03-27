MSP430FanCtrl
=============

MSP430 Fan Controller

Thursday 27 MAR 2014
  Use MSP "G" 2231 for developmemt. Final will use MSP "F"xxxx
  Set up watchdog ISR w/ 1ms period
     Temperature read on  board chip in watchdog ISR
  PWM set using two hardware registers
  Fan at full speed is 633 Hz -->1.5ms period
  
  Fan speed monitor using watchdog timer. Every ~100 cycles look at and reset counter
  Hardware ISR increments counter on rising edge of Tach Input.
  At full speed, expect ~63 counts. At Mid speed expect 31 counts.
  
  8 bit.    I2C Sets: use register, value both 8 bit
  I2C Reads: use register, value.
  
  PINS
    1.0 Tach input
    1.2 PWM output
    1.4&1.5 strap (slave addr)
    1.6 SCL
    1.7 SCD
    
  Temp, 10 bit adc expect .4 deg res.
  MCLK -- set to 1 MHz
   SMCLK div 4 --> 250 KHz
   Watchdog 
   TimerA = SMCLK /8 = 31.25 KHz
   
    
  
