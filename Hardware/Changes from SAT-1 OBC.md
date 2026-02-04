# Changes from SAT-1 OBC

* RP2040 added as co-processor. ANT connections are through this processor instead of through the STM32.
   * SPI1 on the STM32 has been re-assigned to the RP2040 for simplicity of notation, and SPI2 on the STM32 has been assigned to the flash memory / FRAM (though the GPIO chip-select lines remain the same).
   * The RP2040 has been assigned its own oscillator and flash memory. This could change in future.
* Temperature sensor STDS75 has gone obsolete. Using manufacturer-recommended replacement STTS22H instead.
* Header pins for jumpers have been placed on the 3V3, 5V, and 12V lines where they enter the OBC to allow for easier current measurement.
* On the PC104 header, H1 pins 33 and 35 have been assigned to the ADCS UART connections instead of being connected to ground (in parallel with H1 pin 37) via a 100K resistor. The STM32 spare UART connection has been used for this.
* FRAM memory chip CY15B108QN-40LPXI has gone obsolete. Chips have been removed because they were unused in CTS-SAT-1. 
* STM32 25MHz clock ECS-TXO-2520-33-250-AN-TR has no stock available at DigiKey or Mouser. TODO: Replacement to be determined...
* 