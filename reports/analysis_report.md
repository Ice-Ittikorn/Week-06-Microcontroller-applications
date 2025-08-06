<img width="1006" height="586" alt="ภาพถ่ายหน้าจอ 2568-08-06 เวลา 09 53 11" src="https://github.com/user-attachments/assets/375d683d-277c-453a-bac1-0465fccef3a4" />

root@1f1924b19b1a:/project/lab6_1_basic_build# idf.py qemu moniter
Adding "qemu"'s dependency "all" to list of commands with default set of options.
Executing action: all (aliases: build)
Running ninja in directory /project/lab6_1_basic_build/build
Executing "ninja all"...
[1/1] cd /project/lab6_1_basic_build/build/bootloader/esp-idf/esptool_py &...tloader 0x1000 /project/lab6_1_basic_build/build/bootloader/bootloader.bin
Bootloader binary size 0x66a0 bytes. 0x960 bytes (8%) free.
[8/9] Generating binary image from built executable
esptool.py v4.9.0
Creating esp32 image...
Merged 2 ELF sections
Successfully created esp32 image.
Generated /project/lab6_1_basic_build/build/lab6_1_basic_build.bin
[9/9] cd /project/lab6_1_basic_build/build/esp-idf/esptool_py && /opt/esp/...rtition-table.bin /project/lab6_1_basic_build/build/lab6_1_basic_build.bin
lab6_1_basic_build.bin binary size 0x27b20 bytes. Smallest app partition is 0x100000 bytes. 0xd84e0 bytes (84%) free.
Executing action: qemu
Generating flash image: /project/lab6_1_basic_build/build/qemu_flash.bin
esptool.py --chip=esp32 merge_bin --output=/project/lab6_1_basic_build/build/qemu_flash.bin --fill-flash-size=2MB --flash_mode dio --flash_freq 40m --flash_size 2MB 0x1000 bootloader/bootloader.bin 0x10000 lab6_1_basic_build.bin 0x8000 partition_table/partition-table.bin
esptool.py v4.9.0
SHA digest in image updated
Wrote 0x200000 bytes to file /project/lab6_1_basic_build/build/qemu_flash.bin, ready to flash to offset 0x0
Using existing efuse image: /project/lab6_1_basic_build/build/qemu_efuse.bin
Running qemu (fg): qemu-system-xtensa -M esp32 -m 4M -drive file=/project/lab6_1_basic_build/build/qemu_flash.bin,if=mtd,format=raw -drive file=/project/lab6_1_basic_build/build/qemu_efuse.bin,if=none,format=raw,id=efuse -global driver=nvram.esp32.efuse,property=drive,value=efuse -global driver=timer.esp32.timg,property=wdt_disable,value=true -nic user,model=open_eth -nographic -serial mon:stdio
Adding SPI flash device
ets Jul 29 2019 12:21:46

rst:0x1 (POWERON_RESET),boot:0x12 (SPI_FAST_FLASH_BOOT)
configsip: 0, SPIWP:0xee
clk_drv:0x00,q_drv:0x00,d_drv:0x00,cs0_drv:0x00,hd_drv:0x00,wp_drv:0x00
mode:DIO, clock div:2
load:0x3fff0030,len:6372
load:0x40078000,len:15928
load:0x40080400,len:3880
entry 0x40080638
I (736) boot: ESP-IDF v6.0-dev-1002-gbfe5caf58f 2nd stage bootloader
I (737) boot: compile time Aug  6 2025 02:42:22
I (738) boot: Multicore bootloader
I (825) boot: chip revision: v3.0
I (827) boot.esp32: SPI Speed      : 40MHz
I (827) boot.esp32: SPI Mode       : DIO
I (827) boot.esp32: SPI Flash Size : 2MB
I (840) boot: Enabling RNG early entropy source...
I (854) boot: Partition Table:
I (855) boot: ## Label            Usage          Type ST Offset   Length
I (855) boot:  0 nvs              WiFi data        01 02 00009000 00006000
I (855) boot:  1 phy_init         RF data          01 01 0000f000 00001000
I (856) boot:  2 factory          factory app      00 00 00010000 00100000
I (865) boot: End of partition table
I (945) esp_image: segment 0: paddr=00010020 vaddr=3f400020 size=09534h ( 38196) map
I (986) esp_image: segment 1: paddr=0001955c vaddr=3ff80000 size=00024h (    36) load
I (1023) esp_image: segment 2: paddr=00019588 vaddr=3ffb0000 size=025e0h (  9696) load
I (1060) esp_image: segment 3: paddr=0001bb70 vaddr=40080000 size=044a8h ( 17576) load
I (1102) esp_image: segment 4: paddr=00020020 vaddr=400d0020 size=0efb8h ( 61368) map
I (1143) esp_image: segment 5: paddr=0002efe0 vaddr=400844a8 size=08b10h ( 35600) load
I (1277) boot: Loaded app from partition at offset 0x10000
I (1278) boot: Disabling RNG early entropy source...
I (1302) cpu_start: Multicore app
I (2274) cpu_start: Pro cpu start user code
I (2275) cpu_start: cpu freq: 160000000 Hz
I (2275) app_init: Application information:
I (2275) app_init: Project name:     lab6_1_basic_build
I (2275) app_init: App version:      1
I (2276) app_init: Compile time:     Aug  6 2025 02:42:18
I (2276) app_init: ELF file SHA256:  d6da63cce...
I (2276) app_init: ESP-IDF:          v6.0-dev-1002-gbfe5caf58f
I (2277) efuse_init: Min chip rev:     v0.0
I (2277) efuse_init: Max chip rev:     v3.99 
I (2277) efuse_init: Chip rev:         v3.0
I (2278) heap_init: Initializing. RAM available for dynamic allocation:
I (2279) heap_init: At 3FFAE6E0 len 00001920 (6 KiB): DRAM
I (2279) heap_init: At 3FFB2EA8 len 0002D158 (180 KiB): DRAM
I (2280) heap_init: At 3FFE0440 len 00003AE0 (14 KiB): D/IRAM
I (2280) heap_init: At 3FFE4350 len 0001BCB0 (111 KiB): D/IRAM
I (2280) heap_init: At 4008CFB8 len 00013048 (76 KiB): IRAM
I (2319) spi_flash: detected chip: winbond
I (2327) spi_flash: flash io: dio
I (2339) main_task: Started on CPU0
I (2349) main_task: Calling app_main()
I (2349) LAB1: === Build Information ===
I (2349) LAB1: Project Name: lab6_1_basic_build
I (2349) LAB1: ESP-IDF Version: v6.0-dev-1002-gbfe5caf58f
I (2349) LAB1: Compile Date: Aug  6 2025
I (2349) LAB1: Compile Time: 03:02:57
I (2349) LAB1: Chip Model: esp32
I (2349) LAB1: Free Heap: 304636 bytes
I (2349) LAB1: Running... Counter: 0
I (3349) LAB1: Running... Counter: 1
I (4349) LAB1: Running... Counter: 2
I (5349) LAB1: Running... Counter: 3
I (6349) LAB1: Running... Counter: 4
I (7349) LAB1: Running... Counter: 5
I (8349) LAB1: Running... Counter: 6
I (9349) LAB1: Running... Counter: 7
I (10349) LAB1: Running... Counter: 8
I (11349) LAB1: Running... Counter: 9
I (11349) LAB1: Current free heap: 304636 bytes
I (12349) LAB1: Running... Counter: 10
I (13349) LAB1: Running... Counter: 11
I (14349) LAB1: Running... Counter: 12
I (15349) LAB1: Running... Counter: 13
I (16349) LAB1: Running... Counter: 14
I (17349) LAB1: Running... Counter: 15
I (18349) LAB1: Running... Counter: 16
I (19349) LAB1: Running... Counter: 17
I (20349) LAB1: Running... Counter: 18
I (21349) LAB1: Running... Counter: 19
I (21349) LAB1: Current free heap: 304636 bytes
I (22349) LAB1: Running... Counter: 20
I (23349) LAB1: Running... Counter: 21
I (24349) LAB1: Running... Counter: 22
I (25359) LAB1: Running... Counter: 23
I (26359) LAB1: Running... Counter: 24
I (27359) LAB1: Running... Counter: 25
I (28359) LAB1: Running... Counter: 26
I (29359) LAB1: Running... Counter: 27
I (30359) LAB1: Running... Counter: 28
I (31359) LAB1: Running... Counter: 29
I (31359) LAB1: Current free heap: 304636 bytes
I (32359) LAB1: Running... Counter: 30
I (33359) LAB1: Running... Counter: 31
I (34359) LAB1: Running... Counter: 32
I (35359) LAB1: Running... Counter: 33
I (36359) LAB1: Running... Counter: 34
I (37359) LAB1: Running... Counter: 35
I (38359) LAB1: Running... Counter: 36
I (39359) LAB1: Running... Counter: 37
I (40359) LAB1: Running... Counter: 38
I (41359) LAB1: Running... Counter: 39
I (41359) LAB1: Current free heap: 304636 bytes
I (42359) LAB1: Running... Counter: 40
I (43359) LAB1: Running... Counter: 41
I (44359) LAB1: Running... Counter: 42
I (45359) LAB1: Running... Counter: 43
I (46359) LAB1: Running... Counter: 44
I (47359) LAB1: Running... Counter: 45
I (48359) LAB1: Running... Counter: 46
I (49359) LAB1: Running... Counter: 47
I (50359) LAB1: Running... Counter: 48
I (51359) LAB1: Running... Counter: 49
I (51369) LAB1: Current free heap: 304636 bytes
<img width="1440" height="900" alt="ภาพถ่ายหน้าจอ 2568-08-06 เวลา 10 06 09" src="https://github.com/user-attachments/assets/ee564bf1-a76b-4d7e-85a2-fa3f4cfae9d1" />
<img width="1440" height="900" alt="ภาพถ่ายหน้าจอ 2568-08-06 เวลา 10 06 16" src="https://github.com/user-attachments/assets/9c06e06c-0507-4e13-8775-b2901058369d" />

