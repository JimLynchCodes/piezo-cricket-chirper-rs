# piezo-cricket-chirper-rs
An embedded Rust example of a "cricket chirper" made with the Sunfounder Kepler Kit's piezo buzzer, raspberry pi, AA battery pack, and includes logging using an UART cable (sold seperately).

build:
```
cargo build --release
```

convert to a .uf2 file:
```
elf2uf2-rs target/thumbv6m-none-eabi/release/pico-buzzer
```

Note: if you don't have elf2uf2-rs, it can be installed like this:
```
cargo install elf2uf2-rs
```

Then follow the bootsel pi pico process for flashing new firmware:

# Flash to Pico:
# 1. Hold BOOTSEL button
# 2. Plug in USB
# 3. Copy firmware.uf2 to RPI-RP2 drive
# 4. Pico reboots and runs immediately


## UART Logging

find the correct file:
```
ls /dev/tty.usbserial*
```

then use `screen` to view the logs in real-time:
```
screen /dev/tty.usbserial-11111 115200
```

