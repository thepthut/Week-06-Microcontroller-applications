~~~

Executing action: size-files
Running ninja in directory /project/lab6_1_basic_build/build
Executing "ninja all"...
[1/4] cd /project/lab6_1_basic_build/build && /opt/esp/python_env/idf6.0_py3.12_env/bin/python /opt/esp/idf/components/partition_table/check_sizes.py --offset 0x8000 partition --type app /project/lab6_1_basic_build/build/partition_table/partition-table.bin /project/lab6_1_basic_build/build/lab6_1_basic_build.bin
lab6_1_basic_build.bin binary size 0x27b70 bytes. Smallest app partition is 0x100000 bytes. 0xd8490 bytes (84%) free.
[2/4] Performing build step for 'bootloader'
[1/1] cd /project/lab6_1_basic_build/build/bootloader && /opt/esp/python_env/idf6.0_py3.12_env/bin/python /opt/esp/idf/components/partition_table/check_sizes.py --offset 0x8000 bootloader 0x1000 /project/lab6_1_basic_build/build/bootloader/bootloader.bin
Bootloader binary size 0x6690 bytes. 0x970 bytes (8%) free.
[3/4] No install step for 'bootloader'
[4/4] Completed 'bootloader'
Running ninja in directory /project/lab6_1_basic_build/build
Executing "ninja size-files"...
[0/1] cd /project/lab6_1_basic_build/build && /opt/esp/tools/cmake/3.30.2/bin/cmake -D "IDF_SIZE_TOOL=/opt/esp/python_env/idf6.0_py3.12_env/bin/python;-m;esp_idf_size" -D IDF_SIZE_MODE=--files -D MAP_FILE=/project/lab6_1_basic_build/build/lab6_1_basic_build.map -D OUTPUT_JSON= -P /opt/esp/idf/tools/cmake/run_size_tool.cmake
                                                                                   Per-file contributions to ELF file                                                                                    
┏━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━┳━━━━━━┳━━━━━━┳━━━━━━━┳━━━━━━┳━━━━━━━┳━━━━━━━━━━┳━━━━━━━━━━━━┳━━━━━━━┳━━━━━━━━━━━━┳━━━━━━━━━┳━━━━━━━━━━┳━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━┳━━━━━━━━━━━━━┓
┃ Object File                         ┃ Total Size ┃ DRAM ┃ .bss ┃ .data ┃ IRAM ┃ .text ┃ .vectors ┃ Flash Code ┃ .text ┃ Flash Data ┃ .rodata ┃ .appdesc ┃ RTC SLOW ┃ .rtc_slow_reserved ┃ .force_slow ┃
┡━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━╇━━━━━━╇━━━━━━╇━━━━━━━╇━━━━━━╇━━━━━━━╇━━━━━━━━━━╇━━━━━━━━━━━━╇━━━━━━━╇━━━━━━━━━━━━╇━━━━━━━━━╇━━━━━━━━━━╇━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━━━╇━━━━━━━━━━━━━┩
│ esp_app_desc.c.obj                  │      26914 │   10 │   10 │     0 │    0 │     0 │        0 │        417 │   417 │      26487 │   26231 │      256 │        0 │                  0 │           0 │
│ libc_a-vfprintf.o                   │      13396 │    0 │    0 │     0 │    0 │     0 │        0 │      12824 │ 12824 │        572 │     572 │        0 │        0 │                  0 │           0 │
│ tasks.c.obj                         │       9565 │  718 │  696 │    22 │ 8300 │  8300 │        0 │          0 │     0 │        547 │     547 │        0 │        0 │                  0 │           0 │
│ tlsf.c.obj                          │       6833 │    0 │    0 │     0 │ 5358 │  5358 │        0 │       1199 │  1199 │        276 │     276 │        0 │        0 │                  0 │           0 │
│ uart_vfs.c.obj                      │       4966 │  148 │   20 │   128 │    0 │     0 │        0 │       4469 │  4469 │        349 │     349 │        0 │        0 │                  0 │           0 │
│ port.c.obj                          │       4322 │ 3124 │   40 │  3084 │ 1124 │  1124 │        0 │          0 │     0 │         74 │      74 │        0 │        0 │                  0 │           0 │
│ wdt_hal_iram.c.obj                  │       3867 │ 2341 │    0 │  2341 │ 1526 │  1526 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ esp_mmu_map.c.obj                   │       3720 │  132 │  128 │     4 │  777 │   777 │        0 │       2669 │  2669 │        142 │     142 │        0 │        0 │                  0 │           0 │
│ libc_a-dtoa.o                       │       3626 │    0 │    0 │     0 │    0 │     0 │        0 │       3626 │  3626 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ vfs.c.obj                           │       3416 │  232 │   40 │   192 │    0 │     0 │        0 │       3169 │  3169 │         15 │      15 │        0 │        0 │                  0 │           0 │
│ spi_flash_chip_generic.c.obj        │       3241 │  250 │    0 │   250 │ 2991 │  2991 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ rtc_clk.c.obj                       │       2857 │   78 │    4 │    74 │ 2779 │  2779 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ uart.c.obj                          │       2786 │  188 │   12 │   176 │    0 │     0 │        0 │       2346 │  2346 │        252 │     252 │        0 │        0 │                  0 │           0 │
│ intr_alloc.c.obj                    │       2628 │   30 │   22 │     8 │  583 │   583 │        0 │       1910 │  1910 │        105 │     105 │        0 │        0 │                  0 │           0 │
│ queue.c.obj                         │       2467 │    0 │    0 │     0 │ 2194 │  2194 │        0 │          0 │     0 │        273 │     273 │        0 │        0 │                  0 │           0 │
│ libc_a-mprec.o                      │       2260 │    0 │    0 │     0 │    0 │     0 │        0 │       2008 │  2008 │        252 │     252 │        0 │        0 │                  0 │           0 │
│ spi_flash_hal_iram.c.obj            │       2101 │    0 │    0 │     0 │ 2101 │  2101 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ task_wdt.c.obj                      │       2034 │   38 │    5 │    33 │    0 │     0 │        0 │       1881 │  1881 │        115 │     115 │        0 │        0 │                  0 │           0 │
│ esp_err_to_name.c.obj               │       1841 │    0 │    0 │     0 │    0 │     0 │        0 │         51 │    51 │       1790 │    1790 │        0 │        0 │                  0 │           0 │
│ xtensa_vectors.S.obj                │       1801 │   20 │    0 │    20 │ 1745 │  1318 │      427 │          0 │     0 │         36 │      36 │        0 │        0 │                  0 │           0 │
│ mmu_hal.c.obj                       │       1607 │  206 │    0 │   206 │ 1401 │  1401 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ periph_ctrl.c.obj                   │       1597 │   42 │   34 │     8 │  107 │   107 │        0 │       1427 │  1427 │         21 │      21 │        0 │        0 │                  0 │           0 │
│ cpu_start.c.obj                     │       1391 │    5 │    5 │     0 │  599 │   599 │        0 │        779 │   779 │          8 │       8 │        0 │        0 │                  0 │           0 │
│ rtc_time.c.obj                      │       1237 │    0 │    0 │     0 │ 1200 │  1200 │        0 │          0 │     0 │         37 │      37 │        0 │        0 │                  0 │           0 │
│ esp_flash_api.c.obj                 │       1172 │   30 │    0 │    30 │  946 │   946 │        0 │         16 │    16 │        180 │     180 │        0 │        0 │                  0 │           0 │
│ rtc_io_periph.c.obj                 │       1168 │    0 │    0 │     0 │    0 │     0 │        0 │          0 │     0 │       1168 │    1168 │        0 │        0 │                  0 │           0 │
│ ringbuf.c.obj                       │       1150 │    0 │    0 │     0 │ 1053 │  1053 │        0 │          0 │     0 │         97 │      97 │        0 │        0 │                  0 │           0 │
│ heap_caps_base.c.obj                │       1115 │    0 │    0 │     0 │ 1053 │  1053 │        0 │          0 │     0 │         62 │      62 │        0 │        0 │                  0 │           0 │
│ spi_flash_chip_winbond.c.obj        │       1092 │  140 │    0 │   140 │  952 │   952 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ panic_arch.c.obj                    │       1091 │    0 │    0 │     0 │    0 │     0 │        0 │        803 │   803 │        288 │     288 │        0 │        0 │                  0 │           0 │
│ bootloader_flash.c.obj              │       1084 │    0 │    0 │     0 │ 1044 │  1044 │        0 │          0 │     0 │         40 │      40 │        0 │        0 │                  0 │           0 │
│ rtc_init.c.obj                      │       1083 │    0 │    0 │     0 │    0 │     0 │        0 │       1083 │  1083 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ xtensa_intr_asm.S.obj               │       1075 │ 1024 │    0 │  1024 │   51 │    51 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ bootloader_flash_config_esp32.c.obj │       1057 │    0 │    0 │     0 │  971 │   971 │        0 │         86 │    86 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ esp_ipc.c.obj                       │       1038 │  402 │   66 │   336 │  267 │   267 │        0 │        343 │   343 │         26 │      26 │        0 │        0 │                  0 │           0 │
│ locks.c.obj                         │       1019 │  176 │  168 │     8 │  613 │   613 │        0 │        137 │   137 │         93 │      93 │        0 │        0 │                  0 │           0 │
│ memory_layout.c.obj                 │       1016 │    0 │    0 │     0 │    0 │     0 │        0 │          0 │     0 │       1016 │    1016 │        0 │        0 │                  0 │           0 │
│ cache_utils.c.obj                   │        980 │   18 │   14 │     4 │  734 │   734 │        0 │         81 │    81 │        147 │     147 │        0 │        0 │                  0 │           0 │
│ panic.c.obj                         │        968 │   25 │    5 │    20 │   30 │    30 │        0 │        897 │   897 │         16 │      16 │        0 │        0 │                  0 │           0 │
│ heap_caps_init.c.obj                │        961 │    4 │    4 │     0 │    0 │     0 │        0 │        900 │   900 │         57 │      57 │        0 │        0 │                  0 │           0 │
│ partition.c.obj                     │        889 │    8 │    8 │     0 │    0 │     0 │        0 │        844 │   844 │         37 │      37 │        0 │        0 │                  0 │           0 │
│ nullfs.c.obj                        │        878 │    4 │    4 │     0 │    0 │     0 │        0 │        746 │   746 │        128 │     128 │        0 │        0 │                  0 │           0 │
│ multi_heap.c.obj                    │        792 │    0 │    0 │     0 │  515 │   515 │        0 │        228 │   228 │         49 │      49 │        0 │        0 │                  0 │           0 │
│ clk.c.obj                           │        778 │    0 │    0 │     0 │    0 │     0 │        0 │        765 │   765 │         13 │      13 │        0 │        0 │                  0 │           0 │
│ log_binary_heap.c.obj               │        760 │  260 │  260 │     0 │    0 │     0 │        0 │        476 │   476 │         24 │      24 │        0 │        0 │                  0 │           0 │
│ heap_caps.c.obj                     │        744 │    8 │    4 │     4 │  414 │   414 │        0 │        219 │   219 │        103 │     103 │        0 │        0 │                  0 │           0 │
│ libc_a-fseeko.o                     │        718 │    0 │    0 │     0 │    0 │     0 │        0 │        718 │   718 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ libc_a-fvwrite.o                    │        703 │    0 │    0 │     0 │    0 │     0 │        0 │        703 │   703 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ esp_rom_gpio.c.obj                  │        686 │    0 │    0 │     0 │  130 │   130 │        0 │          0 │     0 │        556 │     556 │        0 │        0 │                  0 │           0 │
│ clk_tree_hal.c.obj                  │        679 │    0 │    0 │     0 │    0 │     0 │        0 │        621 │   621 │         58 │      58 │        0 │        0 │                  0 │           0 │
│ vfs_console.c.obj                   │        677 │   16 │   16 │     0 │    0 │     0 │        0 │        481 │   481 │        180 │     180 │        0 │        0 │                  0 │           0 │
│ portasm.S.obj                       │        638 │    0 │    0 │     0 │  638 │   638 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ esp_cpu_intr.c.obj                  │        611 │    0 │    0 │     0 │    0 │     0 │        0 │         77 │    77 │        534 │     534 │        0 │        0 │                  0 │           0 │
│ time.c.obj                          │        585 │   20 │   20 │     0 │    0 │     0 │        0 │        565 │   565 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ memory_layout_utils.c.obj           │        576 │    0 │    0 │     0 │    0 │     0 │        0 │        549 │   549 │         27 │      27 │        0 │        0 │                  0 │           0 │
│ system_internal.c.obj               │        533 │    0 │    0 │     0 │  517 │   517 │        0 │          0 │     0 │         16 │      16 │        0 │        0 │                  0 │           0 │
│ panic_handler.c.obj                 │        521 │    8 │    8 │     0 │   63 │    63 │        0 │        450 │   450 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ esp_ipc_isr.c.obj                   │        518 │   44 │   32 │    12 │  409 │   409 │        0 │         35 │    35 │         30 │      30 │        0 │        0 │                  0 │           0 │
│ esp_clk_tree_common.c.obj           │        511 │    8 │    8 │     0 │    0 │     0 │        0 │        440 │   440 │         63 │      63 │        0 │        0 │                  0 │           0 │
│ cache_hal_esp32.c.obj               │        499 │   38 │    8 │    30 │  461 │   461 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ debug_helpers.c.obj                 │        498 │    0 │    0 │     0 │  498 │   498 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ memspi_host_driver.c.obj            │        488 │   95 │    0 │    95 │  393 │   393 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ spi_flash_hal.c.obj                 │        484 │    0 │    0 │     0 │    0 │     0 │        0 │        484 │   484 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ libc_a-svfiprintf.o                 │        472 │    0 │    0 │     0 │    0 │     0 │        0 │          0 │     0 │        472 │     472 │        0 │        0 │                  0 │           0 │
│ spi_flash_os_func_app.c.obj         │        469 │   56 │    0 │    56 │  336 │   336 │        0 │         52 │    52 │         25 │      25 │        0 │        0 │                  0 │           0 │
│ rtc_module.c.obj                    │        459 │   28 │    4 │    24 │  188 │   188 │        0 │        243 │   243 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ freertos_hooks.c.obj                │        457 │  136 │  128 │     8 │   43 │    43 │        0 │        278 │   278 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ spi_flash_chip_gd.c.obj             │        442 │  127 │    0 │   127 │  315 │   315 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ crosscore_int.c.obj                 │        440 │   16 │    8 │     8 │  248 │   248 │        0 │        130 │   130 │         46 │      46 │        0 │        0 │                  0 │           0 │
│ esp_clk_tree.c.obj                  │        432 │    0 │    0 │     0 │    0 │     0 │        0 │        403 │   403 │         29 │      29 │        0 │        0 │                  0 │           0 │
│ esp_flash_spi_init.c.obj            │        427 │   88 │    4 │    84 │    0 │     0 │        0 │        301 │   301 │         38 │      38 │        0 │        0 │                  0 │           0 │
│ newlib_init.c.obj                   │        402 │  144 │    0 │   144 │    0 │     0 │        0 │        258 │   258 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ app_startup.c.obj                   │        400 │    1 │    1 │     0 │    0 │     0 │        0 │        367 │   367 │         32 │      32 │        0 │        0 │                  0 │           0 │
│ xtensa_context.S.obj                │        394 │    0 │    0 │     0 │  394 │   394 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ flash_mmap.c.obj                    │        394 │    0 │    0 │     0 │  122 │   122 │        0 │        255 │   255 │         17 │      17 │        0 │        0 │                  0 │           0 │
│ sleep_modes.c.obj                   │        378 │  120 │    0 │   120 │    0 │     0 │        0 │        186 │   186 │         36 │      36 │        0 │       36 │                  0 │          36 │
│ esp_clk.c.obj                       │        372 │    9 │    0 │     9 │  339 │   339 │        0 │          0 │     0 │          0 │       0 │        0 │       24 │                 24 │           0 │
│ libc_a-locale.o                     │        368 │    4 │    0 │     4 │    0 │     0 │        0 │          0 │     0 │        364 │     364 │        0 │        0 │                  0 │           0 │
│ esp_timer_impl_lac.c.obj            │        357 │    0 │    0 │     0 │  114 │   114 │        0 │        243 │   243 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ uart_hal_iram.c.obj                 │        356 │    0 │    0 │     0 │    0 │     0 │        0 │        316 │   316 │         40 │      40 │        0 │        0 │                  0 │           0 │
│ assert.c.obj                        │        352 │    0 │    0 │     0 │  352 │   352 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ uart_hal.c.obj                      │        351 │    0 │    0 │     0 │    0 │     0 │        0 │        351 │   351 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ brownout.c.obj                      │        350 │   51 │    4 │    47 │  215 │   215 │        0 │         79 │    79 │          5 │       5 │        0 │        0 │                  0 │           0 │
│ cpu.c.obj                           │        350 │    0 │    0 │     0 │  284 │   284 │        0 │         36 │    36 │         30 │      30 │        0 │        0 │                  0 │           0 │
│ startup.c.obj                       │        348 │   11 │   11 │     0 │   42 │    42 │        0 │        287 │   287 │          8 │       8 │        0 │        0 │                  0 │           0 │
│ int_wdt.c.obj                       │        335 │    9 │    9 │     0 │  104 │   104 │        0 │        222 │   222 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ task_wdt_impl_timergroup.c.obj      │        335 │   12 │   12 │     0 │   31 │    31 │        0 │        292 │   292 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ libc_a-findfp.o                     │        324 │  324 │  312 │    12 │    0 │     0 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ windowspill_asm.o                   │        311 │    0 │    0 │     0 │  311 │   311 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ esp_efuse_startup.c.obj             │        302 │    0 │    0 │     0 │    0 │     0 │        0 │        246 │   246 │         56 │      56 │        0 │        0 │                  0 │           0 │
│ startup_funcs.c.obj                 │        280 │    0 │    0 │     0 │    0 │     0 │        0 │        208 │   208 │         72 │      72 │        0 │        0 │                  0 │           0 │
│ list.c.obj                          │        279 │    0 │    0 │     0 │  279 │   279 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ libc_a-refill.o                     │        277 │    0 │    0 │     0 │    0 │     0 │        0 │        277 │   277 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ spi_flash_encrypt_hal_iram.c.obj    │        276 │   36 │    0 │    36 │  240 │   240 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ interrupts.c.obj                    │        276 │    0 │    0 │     0 │    0 │     0 │        0 │          0 │     0 │        276 │     276 │        0 │        0 │                  0 │           0 │
│ sleep_gpio.c.obj                    │        255 │    0 │    0 │     0 │    0 │     0 │        0 │        227 │   227 │         28 │      28 │        0 │        0 │                  0 │           0 │
│ libc_a-makebuf.o                    │        246 │    0 │    0 │     0 │    0 │     0 │        0 │        246 │   246 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ libc_a-impure.o                     │        244 │  244 │    0 │   244 │    0 │     0 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ esp_time_impl.c.obj                 │        242 │   12 │   12 │     0 │  122 │   122 │        0 │        108 │   108 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ spi_flash_chip_issi.c.obj           │        240 │  129 │    0 │   129 │  111 │   111 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ flash_ops.c.obj                     │        238 │   12 │    4 │     8 │   33 │    33 │        0 │        171 │   171 │         22 │      22 │        0 │        0 │                  0 │           0 │
│ spi_flash_chip_mxic.c.obj           │        238 │  129 │    0 │   129 │  109 │   109 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ spi_flash_chip_drivers.c.obj        │        234 │   28 │    0 │    28 │    0 │     0 │        0 │        206 │   206 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ libc_a-fopen.o                      │        231 │    0 │    0 │     0 │    0 │     0 │        0 │        231 │   231 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ libc_a-reent.o                      │        220 │    0 │    0 │     0 │    0 │     0 │        0 │        220 │   220 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ brownout_hal.c.obj                  │        196 │    0 │    0 │     0 │    0 │     0 │        0 │        196 │   196 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ regi2c_ctrl.c.obj                   │        188 │    8 │    0 │     8 │  180 │   180 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ heap_idf.c.obj                      │        185 │    0 │    0 │     0 │  185 │   185 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ esp_ota_ops.c.obj                   │        183 │    4 │    4 │     0 │    0 │     0 │        0 │        149 │   149 │         30 │      30 │        0 │        0 │                  0 │           0 │
│ libc_a-wsetup.o                     │        168 │    0 │    0 │     0 │    0 │     0 │        0 │        168 │   168 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ efuse_hal.c.obj                     │        164 │    0 │    0 │     0 │  164 │   164 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ highint_hdl.S.obj                   │        161 │    0 │    0 │     0 │  161 │   161 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ chip_info.c.obj                     │        158 │    0 │    0 │     0 │    0 │     0 │        0 │        158 │   158 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ abort.c.obj                         │        156 │    0 │    0 │     0 │  156 │   156 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ cache_err_int.c.obj                 │        146 │    0 │    0 │     0 │    0 │     0 │        0 │        146 │   146 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ partition_target.c.obj              │        146 │    0 │    0 │     0 │    0 │     0 │        0 │        146 │   146 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ xtensa_intr.c.obj                   │        143 │    0 │    0 │     0 │   26 │    26 │        0 │        117 │   117 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ system_time.c.obj                   │        141 │    8 │    8 │     0 │   31 │    31 │        0 │        102 │   102 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ esp_memory_utils.c.obj              │        139 │    0 │    0 │     0 │  139 │   139 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ esp_err.c.obj                       │        137 │    0 │    0 │     0 │  137 │   137 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ esp_system_chip.c.obj               │        132 │    0 │    0 │     0 │  107 │   107 │        0 │         25 │    25 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ heap.c.obj                          │        131 │    0 │    0 │     0 │  131 │   131 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ log_lock.c.obj                      │        130 │    4 │    4 │     0 │  126 │   126 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ spi_flash_os_func_noos.c.obj        │        130 │   40 │    0 │    40 │   90 │    90 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ libc_a-flags.o                      │        129 │    0 │    0 │     0 │    0 │     0 │        0 │        129 │   129 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ lab6_1_basic_build.c.obj            │        126 │    0 │    0 │     0 │    0 │     0 │        0 │        126 │   126 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ esp_ipc_isr_handler.S.obj           │        123 │   16 │    0 │    16 │  107 │   107 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ heap_align_hw.c.obj                 │        118 │    0 │    0 │     0 │  118 │   118 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ port_common.c.obj                   │        110 │    0 │    0 │     0 │   80 │    80 │        0 │          0 │     0 │         30 │      30 │        0 │        0 │                  0 │           0 │
│ log_timestamp.c.obj                 │        108 │    4 │    4 │     0 │  104 │   104 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ stdatomic.c.obj                     │        107 │    8 │    0 │     8 │   99 │    99 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ esp_system.c.obj                    │        106 │   20 │   20 │     0 │    0 │     0 │        0 │         86 │    86 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ esp_cache_msync.c.obj               │        102 │   24 │    0 │    24 │   78 │    78 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ libm_a-s_frexp.o                    │         99 │    0 │    0 │     0 │    0 │     0 │        0 │         99 │    99 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ esp_rom_serial_output.c.obj         │         96 │    0 │    0 │     0 │   96 │    96 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ tag_log_level.c.obj                 │         86 │    0 │    0 │     0 │   17 │    17 │        0 │         69 │    69 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ flash_brownout_hook.c.obj           │         76 │    2 │    2 │     0 │   74 │    74 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ mpu_hal.c.obj                       │         76 │    0 │    0 │     0 │    0 │     0 │        0 │         76 │    76 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ esp_ipc_isr_port.c.obj              │         74 │    0 │    0 │     0 │   40 │    40 │        0 │         34 │    34 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ ext_mem_layout.c.obj                │         72 │    0 │    0 │     0 │    0 │     0 │        0 │          0 │     0 │         72 │      72 │        0 │        0 │                  0 │           0 │
│ cpu_region_protect.c.obj            │         71 │    0 │    0 │     0 │    0 │     0 │        0 │         51 │    51 │         20 │      20 │        0 │        0 │                  0 │           0 │
│ log.c.obj                           │         68 │    0 │    0 │     0 │   68 │    68 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ init.c.obj                          │         68 │    0 │    0 │     0 │    0 │     0 │        0 │         44 │    12 │         24 │       8 │        0 │        0 │                  0 │           0 │
│ cache_esp32.c.obj                   │         67 │    8 │    0 │     8 │   59 │    59 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ panic_handler_asm.S.obj             │         64 │    0 │    0 │     0 │   64 │    64 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ state_asm--restore_extra_nw.o       │         62 │    0 │    0 │     0 │   62 │    62 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ state_asm--save_extra_nw.o          │         62 │    0 │    0 │     0 │   62 │    62 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ libc_a-fwalk.o                      │         57 │    0 │    0 │     0 │    0 │     0 │        0 │         57 │    57 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ log_linked_list.c.obj               │         55 │    4 │    4 │     0 │    0 │     0 │        0 │         51 │    51 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ port_systick.c.obj                  │         50 │    0 │    0 │     0 │   50 │    50 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ libc_a-printf.o                     │         50 │    0 │    0 │     0 │    0 │     0 │        0 │         50 │    50 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ reent_init.c.obj                    │         45 │    0 │    0 │     0 │    0 │     0 │        0 │         45 │    45 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ gpio_periph.c.obj                   │         40 │   40 │    0 │    40 │    0 │     0 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ esp_timer_init.c.obj                │         38 │    0 │    0 │     0 │    0 │     0 │        0 │         30 │    30 │          8 │       8 │        0 │        0 │                  0 │           0 │
│ dport_access.c.obj                  │         37 │    0 │    0 │     0 │   37 │    37 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ xtensa_init.c.obj                   │         36 │    4 │    4 │     0 │   32 │    32 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ esp_gpio_reserve.c.obj              │         36 │    8 │    0 │     8 │    0 │     0 │        0 │         28 │    28 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ libc_a-vprintf.o                    │         36 │    0 │    0 │     0 │    0 │     0 │        0 │         36 │    36 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ libc_a-sprint_r.o                   │         34 │    0 │    0 │     0 │    0 │     0 │        0 │         34 │    34 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ sar_periph_ctrl.c.obj               │         32 │    0 │    0 │     0 │    0 │     0 │        0 │         32 │    32 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ libc_a-mbtowc_r.o                   │         32 │    0 │    0 │     0 │    0 │     0 │        0 │         32 │    32 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ interrupts--intlevel.o              │         32 │    0 │    0 │     0 │    0 │     0 │        0 │          0 │     0 │         32 │      32 │        0 │        0 │                  0 │           0 │
│ bootloader_efuse.c.obj              │         30 │    0 │    0 │     0 │   30 │    30 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ esp_cache_utils.c.obj               │         30 │    0 │    0 │     0 │   30 │    30 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ log_level.c.obj                     │         29 │    4 │    0 │     4 │    0 │     0 │        0 │         25 │    25 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ debug_helpers_asm.S.obj             │         29 │    0 │    0 │     0 │   29 │    29 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ syscalls.c.obj                      │         25 │    0 │    0 │     0 │    0 │     0 │        0 │         25 │    25 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ libc_a-sysfcntl.o                   │         25 │    0 │    0 │     0 │    0 │     0 │        0 │         25 │    25 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ libc_a-sysgettod.o                  │         24 │    0 │    0 │     0 │    0 │     0 │        0 │         24 │    24 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ reent_syscalls.c.obj                │         22 │    0 │    0 │     0 │    0 │     0 │        0 │         22 │    22 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ libc_a-fseek.o                      │         21 │    0 │    0 │     0 │    0 │     0 │        0 │         21 │    21 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ esp_rom_sys.c.obj                   │         19 │    0 │    0 │     0 │   19 │    19 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ libc_a-localeconv.o                 │         19 │    0 │    0 │     0 │    0 │     0 │        0 │         19 │    19 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ util.c.obj                          │         18 │    4 │    4 │     0 │   14 │    14 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ libc_a-errno.o                      │         13 │    0 │    0 │     0 │    0 │     0 │        0 │         13 │    13 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ esp_ipc_isr_routines.S.obj          │         10 │    0 │    0 │     0 │   10 │    10 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ flash_encrypt.c.obj                 │         10 │    0 │    0 │     0 │   10 │    10 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ esp_efuse_api.c.obj                 │         10 │    0 │    0 │     0 │    0 │     0 │        0 │         10 │    10 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ pthread.c.obj                       │         10 │    0 │    0 │     0 │    0 │     0 │        0 │         10 │     5 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ int_asm--set_intclear.o             │          8 │    0 │    0 │     0 │    8 │     8 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ bootloader_mem.c.obj                │          8 │    0 │    0 │     0 │    0 │     0 │        0 │          8 │     8 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ esp_efuse_utility.c.obj             │          7 │    0 │    0 │     0 │    0 │     0 │        0 │          7 │     7 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ ubsan.c.obj                         │          5 │    0 │    0 │     0 │    5 │     5 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ clk_utils.c.obj                     │          5 │    0 │    0 │     0 │    5 │     5 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ getentropy.c.obj                    │          5 │    0 │    0 │     0 │    0 │     0 │        0 │          5 │     5 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ pthread_cond_var.c.obj              │          5 │    0 │    0 │     0 │    0 │     0 │        0 │          5 │     5 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ pthread_local_storage.c.obj         │          5 │    0 │    0 │     0 │    0 │     0 │        0 │          5 │     5 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ pthread_rwlock.c.obj                │          5 │    0 │    0 │     0 │    0 │     0 │        0 │          5 │     5 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ pthread_semaphore.c.obj             │          5 │    0 │    0 │     0 │    0 │     0 │        0 │          5 │     5 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ cxx_guards.cpp.obj                  │          5 │    0 │    0 │     0 │    0 │     0 │        0 │          5 │     5 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ cxx_init.cpp.obj                    │          5 │    0 │    0 │     0 │    0 │     0 │        0 │          5 │     5 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ nvs_sec_provider.c.obj              │          5 │    0 │    0 │     0 │    0 │     0 │        0 │          5 │     5 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ phy_override.c.obj                  │          5 │    0 │    0 │     0 │    0 │     0 │        0 │          5 │     5 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ log_write.c.obj                     │          4 │    4 │    0 │     4 │    0 │     0 │        0 │          0 │     0 │          0 │       0 │        0 │        0 │                  0 │           0 │
│ spi_bus_lock.c.obj                  │          4 │    0 │    0 │     0 │    0 │     0 │        0 │          0 │     0 │          4 │       4 │        0 │        0 │                  0 │           0 │
└─────────────────────────────────────┴────────────┴──────┴──────┴───────┴──────┴───────┴──────────┴────────────┴───────┴────────────┴─────────┴──────────┴──────────┴────────────────────┴─────────────┘

~~~
