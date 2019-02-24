# Connecting STM32 Nucleo board to I2C EEPROM 24C01C


WARNING! Work in Progress

Current status:
* green LED after init
* blinking blue LED in `while(1)` loop

# Setup

Required Hardware:
* [STM NUCLEO-F767ZI] development board with Cortex-M7 CPU

Required Software:
* [STM32CubeF7] Firmware package requried to build this project.
  Must be unpacked to `C:\ARM` directory as `c:\ARM\STM32Cube_FW_F7_V1.14.0`.
* [System Workbench for STM32] development IDE

Recommended Software:
* [STM32CubeMX] - this project was generated using this tool.
  You can open `stm32-i2c-24c01c.ioc` project file and customize it.
* Putty to watch info/error messages from ARM program.

# Build


TODO:

# Run/Debug

To see info/error messages on UART you need to:
* get `COMx` port number in `Device Manager`:
  - expand `Ports (COM & LPT)`
  - notice COM port number, for example `STMicroelectronics STLink Virtual COM Port (COM3)`

In Putty: 
* create new connection type `Serial` with:
  - Serial line: `COMx` (replace `x` with your COM port number)
  - Speed: 115200
* in `Connection` -> `Serial` tree use:
  - Data bits: `8`
  - Stop bits: `1`
  - Parity: `None`
  - Flow control: `None`
* apply/save etc... and connect

TODO: 

# Random notes

* `int __io_putchar(int ch)` redefinition (required to redirect `printf(3)`
   to UART will not work until generated `syscalls.c` is added to 
   source files (without it there are hardcoded null stubs, without
   weak symbol `__io_putchar` to be redefined)



[STM32CubeF7]: https://www.st.com/en/embedded-software/stm32cubef7.html
[System Workbench for STM32]: http://www.openstm32.org/System%2BWorkbench%2Bfor%2BSTM32
[STM32CubeMX]: https://www.st.com/content/st_com/en/products/development-tools/software-development-tools/stm32-software-development-tools/stm32-configurators-and-code-generators/stm32cubemx.html
[STM NUCLEO-F767ZI]: https://www.st.com/content/st_com/en/products/evaluation-tools/product-evaluation-tools/mcu-eval-tools/stm32-mcu-eval-tools/stm32-mcu-nucleo/nucleo-f767zi.html
[Getting started with ST NUCLEO F767ZI Board]: https://github.com/hpaluch/hpaluch.github.io/wiki/Getting-started-with-ST-NUCLEO-F767ZI-Board
[STM32CubeF7]: https://www.st.com/en/embedded-software/stm32cubef7.html
[STM32 Nucleo-144 boards]: https://www.st.com/content/ccc/resource/technical/document/user_manual/group0/26/49/90/2e/33/0d/4a/da/DM00244518/files/DM00244518.pdf/jcr:content/translations/en.DM00244518.pdf
[Putty]: https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html
