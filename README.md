<img width="1059" height="668" alt="image" src="https://github.com/user-attachments/assets/fa774a05-f130-4c7e-abeb-44185da7345b" /># PlatformIO_wd_qemu_for_VSD_Sifive
PlatformIO_wd_qemu_for_VSD_Sifivepio 

# Install Riscv_tool_chain
## pkg install --global --tool "platformio/tool-qemu-riscv@^1.40100.190927"

# Run the command for running
## pio test -vvv --without-uploading
## C:\Users\ceeri\.platformio\penv\Scripts\pio.exe test -vvv --without-uploading



# Platform.ini
```
;[env:native]
;platform = native
[env:hifive1]
platform = sifive
framework = freedom-e-sdk
board = hifive1

platform_packages =
    platformio/tool-qemu-riscv
build_flags = -DUNITY_INCLUDE_CONFIG_H
test_testing_command =
    ${platformio.packages_dir}/tool-qemu-riscv/bin/qemu-system-riscv32
    -nographic
    -machine 
    sifive_e
    -kernel
    ${platformio.build_dir}/${this.__env__}/firmware.elf
```
Later run the command 
## pio test -vvv --without-uploading
