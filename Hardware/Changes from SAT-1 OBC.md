# Changes from SAT-1 OBC

* RP2040 added as co-processor. ANT connections are through this processor instead of through the STM32.
* Temperature sensor STDS75 has gone obsolete. Using manufacturer-recommended replacement STTS22H instead.
* Header pins for jumpers have been placed on the 3V3, 5V, and 12V lines where they enter the OBC to allow for easier current measurement.