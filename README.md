# ESP32_Frequency_generation_2MHz_10MHz  
esp32, 想現撿現成的, 請問有沒有開源的ARDUINO 項目, 可以在一個 IO 輸出方波, 頻率範圍 2MHz - 10MHz, 每顆esp32輸出固定的頻率就好. 產生測試訊號用途, 因為要好幾台sig-gen一起出力, 不夠小朋友, 想找便宜的替代方法.  


懶惰, 找到這個,  
https://www.edaboard.com/threads/issues-with-generating-11-mhz-square-wave-on-esp32-esp32-wrover-board.401727/post-1730410   
  
本地存檔 [FFT_on_ESP32_PCM1808_03.zip](FFT_on_ESP32_PCM1808_03.zip)  

試試看行不行, 再來改.  

果然不行, 充滿 BUG 的源碼, 原因??
```
rst:0x1 (POWERON_RESET),boot:0x13 (SPI_FAST_FLASH_BOOT)
flash read err, 1000
Falling back to built-in command interpreter.
OK
>ets Jun  8 2016 00:22:57

rst:0x10 (RTCWDT_RTC_RESET),boot:0x13 (SPI_FAST_FLASH_BOOT)
configsip: 0, SPIWP:0xee
clk_drv:0x00,q_drv:0x00,d_drv:0x00,cs0_drv:0x00,hd_drv:0x00,wp_drv:0x00
mode:DIO, clock div:2
load:0x3fff0030,len:1284
load:0x40078000,len:12808
load:0x40080400,len:3032
entry 0x400805e4

Starting ...ESP32_Frequency_generation_2MHz_10MHz_pin18

E (45) ledc: requested frequency and duty resolution can not be achieved, try reducing freq_hz or duty_resolution. div_param=5

Program Started

```
