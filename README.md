# **研究材料準備與硬體連接教學**

## **材料清單**
在開始實作之前，請確保已準備好以下硬體設備和相關材料。這些元件的選擇是基於 Arduino 生態系統的高通用性和可擴展性，適合初學者及進階開發者進行各類創客項目：

- **Arduino UNO 開發板**：核心微控制器，用於處理數據和控制硬體操作。
- **Ethernet W5100 網路擴展板**：提供有線網路連接功能，適合需要穩定網路的應用場合。
- **MB-102 麵包板**：用於快速搭建和測試電路的無焊接實驗工具。
- **KEYES 光敏電阻**：用於感應環境光照變化，轉換為可處理的電壓信號。
- **YL-69 土壤濕度計**：專為土壤環境設計，用於測量水分含量的模擬感測器。
- **公對公杜邦線**：標準電路接線工具，用於連接不同模組的公接頭。
- **母對母杜邦線**：適合模組之間的母座銜接，提升連接彈性。
- **公對母杜邦線**：解決多樣化連接需求的萬能工具。

這些材料不僅是實作項目的基礎，也是學習如何搭建電子硬體電路的重要資源。相對於傳統焊接方式，使用麵包板及杜邦線能大幅降低接線的失誤率及調試時間，讓您能夠專注於核心功能的實現。

---

## **執行步驟說明**

本教學特別設計了一系列循序漸進的操作步驟，旨在幫助您輕鬆掌握硬體的安裝與連接方法。透過清晰的說明和詳盡的電路指引，您將能快速完成感測器與微控制器的整合，為後續的軟體開發鋪路。

---

### **步驟一：硬體連接詳解**

硬體的正確連接是每個電子項目成功的基石。以下將針對各個感測器模組的連接方式進行逐一說明，確保您能清楚理解每個元件的工作原理和接線方法。

---

### **1. 土壤濕度感測器連接**
土壤濕度感測器（YL-69）是一個專門用於測量土壤含水量的裝置，能夠將類比信號轉換為 Arduino 可讀取的數據。該感測器廣泛應用於智慧農業、自動灌溉系統等場景。

- **VCC** 接至 Arduino 的 **5V**：為感測器供應穩定電壓，以保證數據的精確性。
- **GND** 接至 Arduino 的 **GND**：建立電路的公共地線，確保信號的零基準穩定。
- **SIG（信號腳）** 接至 Arduino 的 **A0（模擬輸入0）**：將感測器的輸出數據傳送至 Arduino 的模擬輸入端口。

> **專業提示**：  
> 在連接 VCC 和 GND 時，請務必檢查杜邦線的接觸是否緊密，以避免因接觸不良造成數據波動或讀取失敗的情況。此外，測試時建議將感測器插入濕潤的土壤中以模擬真實環境。

---

### **2. 光敏電阻（光照感測器）連接**
光敏電阻是一種對光線敏感的電阻元件，其阻值會隨環境光強度的變化而改變。透過分壓電路，光敏電阻能將這些變化轉換為 Arduino 可讀取的電壓信號。

1. 將光敏電阻的一端接至 Arduino 的 **5V**：提供穩定的工作電壓以啟動感測器。
2. 光敏電阻的另一端與 **10kΩ 電阻** 連接，形成分壓電路：分壓電路的作用是將光敏電阻的輸出範圍限制在 Arduino 能處理的電壓範圍內。
3. 分壓電路的連接點（光敏電阻與電阻之間）接至 Arduino 的 **A1（模擬輸入1）**：將光敏電阻的輸出電壓傳送至模擬輸入端口。
4. **10kΩ 電阻** 的另一端接至 Arduino 的 **GND**：為分壓電路提供地線連接。

> **深入分析**：  
> 光敏電阻的工作原理基於光電效應，其阻值隨光照強度增減的特性非常適合用於測量環境光線。例如，在智慧家居中，可以用來自動調節室內的燈光亮度，實現節能效果。

---

### **3. 電路總覽圖**
以下提供了一個簡化的電路總覽圖，幫助您更直觀地了解各元件之間的連接方式。建議在實際搭建時參考麵包板的佈線情況，逐步完成硬體安裝。

```
Arduino Uno
+-------------------+
|                   |
| 5V      GND       |
| |        |        |
| |        |        |
| |        |        |
| A0       A1       |
| |        |        |
| |        |        |
|                   |
+-------------------+

土壤濕度感測器和光敏電阻分別接至 A0 和 A1
```

> **提示與建議**：  
> - 建議在電路搭建完成後，使用萬用表測試電源與地線之間的連續性，確保電路無短路問題。  
> - 若感測器數據異常，請檢查分壓電路中的電阻值是否正確，並確保杜邦線與麵包板插孔的接觸良好。

---

## **參考文獻資料**
本教學內容結合了多個權威參考資料，以提供準確且全面的硬體連接指引。若需進一步了解相關元件的操作及應用，可參考以下資源：

1. **Arduino 教學資源**  
   [Arduino 入門教學 - JMaker](https://blog.jmaker.com.tw/arduino-tutorials/)

2. **W5100 網路模組教學**  
   [W5100 使用教學 - CSJH Maker](https://sites.google.com/site/csjhmaker/w5100you-xian-wang-lu-shi-zuo)

---

## **結語**
透過上述教學，您已完成土壤濕度感測器與光敏電阻的硬體連接，並成功搭建了一個基於 Arduino 的簡單感測電路系統。這套系統具備了環境監控的基本功能，為後續軟體編程及功能拓展提供了堅實的基礎。

值得一提的是，在實驗過程中，若遇到任何問題，請務必反覆檢查電路連接是否正確，並參閱上述參考文獻以尋求進一步指引。未來，您可以將此電路延伸應用於智慧農業、智慧家居或環境監控等更多場景，實現更高層次的技術目標。
