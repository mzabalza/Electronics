# Electronics-basics. PIC32 pins configuration

### 0. TP0
Created a new project and added a new .h containing typedefs for:
- u8, u16 and u32
- s8, s16 and s32

## 1. TP1/ Control of the LED by the button:
- One press on the button lights the LED
- Another button press turns off the led

## 2. TP2/ Blinking of the LED
- The led flashes at the rate of a change of state per second (0.5Hz, 1s on / 1s off).
- Pressing the button doubles the rate of flashing. At 8Hz, pressing the button resets the rhythm to 0.5Hz.
- The "sequence" will be: 0.5Hz, 1Hz, 2Hz, 4Hz, 8hZ, 0.5Hz, 1Hz, ...
- Timer must be used to adjust the flashing speed

## 3. TP3/ Using interruptions
to achieve a  "non-blocking", there is a main loop containing only one statement:
- Clear watchdog, Blinking and button management are activated in an ISR.

## 4. TP4/ DIM of the LED
The program does the same thing, but on a long press (> 2s) the LED goes into DIM mode, in 5s its intensity goes from 0 to 100% then from 100% to 0% (and so on).
For that a PWM is coded on the GPIO which controls the LED.
