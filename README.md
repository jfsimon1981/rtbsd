# rtbsd
Real time mini operating system for micro-controllers

RtBSD is an open source real time mini operating system for microcontrollers. It currently runs on PIC 16F886. Its port is possible to most 8/16 bits other microctrolles such as Atmel, Microchip, ESP, STM, NXP, …

The source code is placed under BSD-3 license.

Supporting the project can be done financially or through purchases at our embedded Electronic store at [lecomptoirelectronique.fr](https://lecomptoirelectronique.fr). MCU/CPUs support and are delivered programmed with RtBSD. 

  * Unordered List Item"Real time" functions must not overflow, they are executed in interrupt context.
    *  User code can be implemented in this context.
  * "Scheduled" functions are stacked. They can be interrupted and executed in successive batches.
    * Main user function is executed in a scheduled 100ms context
  * Task stack overflow is monitored

```
void function_4ms_realtime(void);  // Real time 4 ms period function - Interrupt context
void function_20ms_realtime(void);  // Real time 20 ms period function - Interrupt context
void function_20ms_scheduler(void);  // Scheduled 20 ms period function - Via scheduler
void function_100ms_realtime(void); // Real time 100 ms period function - Interrupt context
void function_100ms_scheduler(void); // Scheduled 100 ms period function - Via scheduler
void function_100ms_user(void); // Scheduled les 100 ms period function - Via scheduler
void function_1s_realtime(void); // Real time 1s - Interrupt context
void function_1s_scheduler(void); // Scheduled 1 s - Via scheduler
```