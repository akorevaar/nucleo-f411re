## Support package for the [Nucleo-f411re](https://www.st.com/en/evaluation-tools/nucleo-f411re.html) board.

### Some dependencies

Assuming you already have cargo, and general embedded development tools (gdb, openocd, libusb-1.0). 
Install the following: 

    cargo install cargo-flash
    cargo install cargo-embed
    rustup target add thumbv7em-none-eabihf
  
For more help, see https://rust-embedded.github.io/cortex-m-quickstart/cortex_m_quickstart/
    
#### Flash using Probe.rs

```cargo flash --chip stm32f411re --example button-interrupt```

Or with cargo embed

```cargo embed --release --example button-rtfm```

If probe fails to flash your board you probably need to update the firmware on the onboard programmer.
The updater can be found at: https://www.st.com/en/development-tools/stsw-link007.html

### Board properties

 * User led on PA5
 * User button on PC13
 * Serial port through ST-LINK on USART2, Tx: PA2 and Rx: PA3.

This repository is based on https://github.com/jkristell/nucleo-f401re 
(which is based on https://github.com/therealprof/stm32f407g-disc)
