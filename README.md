# rtbsd
Real time mini operating system for micro-controllers

RtBSD is an open source real time mini operating system for microcontrollers. It currently runs on PIC 16F886. Its port is possible to most 8/16 bits other microctrolles such as Atmel, Microchip, ESP, STM, NXP, …

“Real time” functions must not overflow, they are executed in interrupt context. User code can be called in this context. “Scheduled” functions are stacked. They can be interrupted and executed in successive batches.

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