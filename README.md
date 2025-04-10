
## 簡介：
> 將考評局認證的Fx-50FH-ii計數機改裝成Game Console，使用無綫充電。
## 原理：
使用了Deltabeard開發的[RP2040-GB](https://github.com/deltabeard/RP2040-GB)，利用Raspberry Pi Pico運行GameBoy模擬器[Peanut-GB](https://github.com/deltabeard/Peanut-GB)搭配`.gb`後綴的ROM文件實現模擬GameBoy的效果，詳細原理可以參考前面兩個專案。
## 所需物品：
- Fx-50FH-ii計數機外殼
- 2.0寸TFT ILI9225 屏幕（自帶Micro SD卡卡槽）
- Raspberry Pi Pico 
- 1500mAh聚合物鋰電池
- 邏輯PCB（包涵按鍵+拓展）
- TP4056充電放電模塊
- 3w無綫充電模塊
- 電源按鈕（自鎖按鈕1208YD）
- 壓克力屏幕蓋板/3D打印屏幕蓋板
- 鍋仔片按鈕5mm*5mm
- M2*3mm螺絲
## 製作指南：
### 硬件： 
於Hardware文件夾中可以檢視，  
當中有gerber文件（`.zip`後綴），可以直接交給PCB生產商生產同款PCB，國内推薦使用嘉立創。  
`.epro`後綴的文件為工程文件，當中包含原理圖以及PCB設計圖，可以使用 立創EDA專業版 打開編輯。  
#### 屏幕部分：
```
    VCC = 3.3V (OUT) 
    GND = GND 
    CS = GP17 
    CLK = GP18 
    SDI = GP19 
    RS = GP20 
    RST = GP21 
    LED = GP22 
```
#### SD卡部分：
```
    MISO = GP12 
    CS = GP13 
    SCK = GP14 
    MOSI = GP15
```
#### 按鍵部分：
```
    上 = GP2 
    下 = GP3  
    左 = GP5  
    右 = GP4  
    A = GP6  
    B = GP7  
    SELECT = GP8  
    START = GP9  
    所有按鈕接地 = GND  
```
#### 電源部分：
```
    邏輯板上BAT- = GND
    電源按鈕負 = VSYS
``` 
#### 電源接綫：
![圖片](https://github.com/WuJoe826/Fx-50FH_ii-GameBoy/blob/main/Images/power_wiring.png "接綫")

### 固件：
#### 準備Raspberry Pi Pico：  
每次燒錄前需要按住Raspberry Pi Pico的`BOOTSEL`按鈕，之後用Micro USB綫鏈接它到你的的電腦，當見到`RPI-RP2`裝置在你的電腦出現便可以鬆開。  
使用了YouMakeTech製作的[Pico-GB](https://github.com/YouMakeTech)Raspberry Pi Pico Gameboy燒錄包（`.uf2`後綴），可以在他的專案的[Release](https://github.com/YouMakeTech/Pico-GB/releases/tag/20230510)裏面下載燒錄文件，下載後直接拖到Raspberry Pi Pico中即可。  
#### 準備SD卡：
！！推薦使用8GB以上的Micro SD卡！！  
把SD卡插入SD卡讀卡器/電腦自備的SD卡槽中，SD卡的格式必須爲`FAT32`。  
然後把你所擁有的.gb後綴ROM文件抄錄到SD卡中即可。  
完成以上後請把Micro SD卡插到2.0寸TFT ILI9225 屏幕的SD卡槽中即可。
### 外觀： 

## 注意事項：
- 請見YouMakeTech的[Pico-GB](https://github.com/YouMakeTech)專案中的Known issues and limitations。

## 免責聲明：
- 對於因爲個人改裝後導致任何損失本人皆不負責。
- 此專案并非教唆各位自行改裝Fx-50FH_ii計數機使其能夠運行除計數功能以外的任何其他功能。
- 此專案并非教唆各位使用改裝後Fx-50FH_ii計數機進行任何不正當的行爲（例如：考試作弊）等行爲。

## 授權許可：
此專案遵守MIT授權協議。
