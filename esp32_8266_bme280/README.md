ESP8266的硬件IIC端口是  D1-- SCL，D2--SDA ；
ESP32  的硬件IIC端口是  P21--SCL，P22--SDA；

BME/BMP280 的物理地址为0x77；
____________________________________________________________________________________________________
| Register Name   | Address | bit7 | bit6 | bit5 | bit4 | bit3 | bit2 | bit1 | bit0 | Reset state  |
| temp_xlsb       | 0xFC    |     temp_xlsb<7:4>        |   0  |   0  |   0  |   0  |     0x00     |----只读
| temp_lsb        | 0xFB    |                       temp_lsb<7:0>                   |     0x00     |----只读
| temp_msb        | 0xFA    |                       temp_msb<7:0>                   |     0x80     |----只读
| press_xlsb      | 0xF9    |      press_xlsb<7:4>      |   0  |   0  |   0  |   0  |     0x00     |----只读
| press_lsb       | 0xF8    |                       press_lsb<7:0>                  |     0x00     |----只读
| press_msb       | 0xF7    |                       press_msb<7:0>                  |     0x80     |----只读
| config          | 0xF5    |        t_sb[2:0]   |      filte[2:0]    |//////|spi[0]|     0x00     |----读写
| ctrl_meas       | 0xF4    |       osrs_t[2:0]  |     osrs_p[2:0]    |  mode[1:0]  |     0x00     |----读写
| status          | 0xF3    |///////////////////////////|meas[0]|////////////|更新[0]|    0x00      |----读写
| reset           | 0xE0    |                     reset[7:0]                        |     0x00     |----只写
| id              | 0xD0    |                     chip_id[7:0]                      |     0x58     |----只读
|calib25...calib00|0xA1…0x88|                   calibration data                    |   individual |----只读
----------------------------------------------------------------------------------------------------
