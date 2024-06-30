# mynewt_nrf51822_qfaa

Mynewt packages with BSP support for nRF51822-QFAA (build code: H2) 256kB Flash, 16kB RAM.
Uses OpenOCD for flashing and debugging.

This is a mix of the original `@apache-mynewt-core/hw/bsp/nrf51-blenano` (for OpenOCD support)
and `@apache-mynewt-core/hw/bsp/nordic_pca10028-16k` (for flash and RAM size).

Given the reduced flash size, the `FLASH_AREA_IMAGE_1` is offset over the actual flash size (0xff023800) making it unusable.
The freed space is used to double the size of `FLASH_AREA_IMAGE_0`. See `hw/bsp/nordic_pca10028-16k-openocd/bsp.yml` for details.