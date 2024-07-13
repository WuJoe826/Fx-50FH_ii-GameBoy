# Fx-50FH_ii-GameBoy
## 簡介：
> 將考評局認證的Fx-50FH-ii計數機改裝成Nintendo GameBoy，可以游玩初代GameBoy游戲。
## 原理：
使用了Deltabeard開發的[RP2040-GB](https://github.com/deltabeard/RP2040-GB)，利用Raspberry Pi Pico運行GameBoy模擬器[Peanut-GB](https://github.com/deltabeard/Peanut-GB)搭配.gb後綴的ROM文件實現模擬GameBoy的效果，詳細原理可以參考前面兩個專案。
## 所需物品：
1. Fx-50FH-ii計數機外殼
2. 2.0寸TFT ILI9225 屏幕
3. Raspberry Pi Pico 
4. 1500mAh聚合物鋰電池
5. 邏輯PCB（包涵按鍵+拓展）
6. TP4056充電放電模塊
7. 3w無綫充電模塊
8. 電源按鈕（自鎖按鈕1208YD）
## 製作指南：
### 硬件： 
於Hardware文件夾中可以檢視， 
當中有gerber文件（.zip後綴），可以直接交給PCB生產商生產同款PCB，國内推薦使用嘉立創。 
.epro後綴的文件為工程文件，當中包含原理圖以及PCB設計圖，可以使用立創eda（普通/專業版）打開編輯。 
原理沒有什麽好說的，就是連連看，把每一條綫路連到他們正確的位置上： 
```
    屏幕部分：

    VCC = 3.3V (OUT) 
    GND = GND 
    CS = GP17 
    CLK = GP18 
    SDI = GP19 
    RS = GP20 
    RST = GP21 
    LED = GP22 

    SD卡部分：

    MISO = GP12 
    CS = GP13 
    SCK = GP14 
    MOSI = GP15

    電源部分：

    TP4056充電放電模塊 輸出正 = 邏輯板上BAT+
    TP4056充電放電模塊 輸出負 = 邏輯板上BAT-
    電池 正極 = TP4056充電放電模塊 電池接口正B+
    電池 負極 = TP4056充電放電模塊 電池接口負B-
    3w無綫充電模塊 輸出正 = TP4056充電放電模塊 輸入接口正
    3w無綫充電模塊 輸出負 = TP4056充電放電模塊 輸入接口負
    邏輯板上BAT+ = 電源按鈕正
    邏輯板上BAT- = GND
    電源按鈕負 = VSYS
```
### 固件：
開發中。。。

