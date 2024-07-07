# Fx-50FH_ii-GameBoy
## 簡介：
> 將考評局認證的Fx-50FH-ii計數機改裝成 Nintendo GameBoy，可以游玩初代GameBoy游戲。
## 所需物品：
1. Fx-50FH-ii計數機 x1  
2. ST7789 170*320 IPS屏幕 x1  
3. Raspberry Pi Pico x1  
4. 聚合物鋰電池 x1  
5. 定制PCB x1
## 原理：
由Deltabeard開發的[RP2040-GB](https://github.com/deltabeard/RP2040-GB)修改而來，修改了ILI9225的屏幕驅動使其可以驅動ST7789屏幕，使用Raspberry Pi Pico運行GameBoy模擬器[Peanut-GB](https://github.com/deltabeard/Peanut-GB)搭配.gb後綴的ROM文件實現模擬GameBoy的效果，詳細原理可以參考上方兩個專案。
