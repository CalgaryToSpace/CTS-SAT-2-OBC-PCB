# Changes from SAT-1 OBC

* RP2040 added as co-processor. ANT connections are through this processor instead of through the STM32.
   * SPI1 on the STM32 has been re-assigned to the RP2040 for simplicity of notation, and SPI2 on the STM32 has been assigned to the flash memory / FRAM (though the GPIO chip-select lines remain the same).
		* (Rationale: this way SPI1 on the RP2040 is connected to SPI1 of the STM32. SPI0 on the RP2040 is not connected to anything.)
   * The RP2040 has been assigned its own oscillator and flash memory. This could change in future.
   * ANT I2C2 and I2C3 lines from the STM32 have been reassigned to I2C0 and I2C1 from the RP2040.
		* To simplify notation, ADCS I2C1 has been reassigned to I2C2, and Temperature Sensor I2C4 had been reassigned to I2C3.
		* (Rationale: this way there is only one each of I2C0, 1, 2, and 3 on the board instead of having 2x I2C1 connected to different things)
* Temperature sensor STDS75 has gone obsolete. Using manufacturer-recommended replacement STTS22H instead.
* FRAM memory chip CY15B108QN-40LPXI has gone obsolete. Chips have been removed because they were unused in CTS-SAT-1. 
* A connector (Picoblade, 4-wide) has been added for the Optical Downlink Payload, which communicates via USART2. 
* Header pins for jumpers have been placed on the 3V3, 5V, and 12V lines where they enter the OBC to allow for easier current measurement.
* On the PC104 header, H1 pins 33 and 35 have been assigned to the ADCS UART connections. They are presently unconnected.
* STM32 25MHz clock ECS-TXO-2520-33-250-AN-TR originally had no stock available at DigiKey, but now has 515. No changes have been made to this.
* STM32 Reset Switch KH-6X6X4.3H-STM is very difficult to find. Replacing with C&K PTS526SK15SMTR2-LFS, which is available at DigiKey.

# Info from Design Reviews
* MPI expects to downlink a lot of data, which might require additional or larger flash memory modules. 
* DP on RP2040 to reset it to a known state in case of bad code?