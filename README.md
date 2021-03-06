# Voronoi Diagram 演算法
中山大學 資訊工程學系 碩士班一年級 M103040086 游辰生

## 軟體規格書
### - 輸入與輸出資料規格
#### 輸入
以滑鼠在600*600的畫布上隨機點擊，最後點擊Run可以產生解果
x軸由左到右漸增
y軸由上到下漸增
四角座標如下所示：
```
(0, 0)          (600, 0)

(600, 0)        (600, 600)
```
點擊 test file，讀入「輸入文字檔」：  
```
3 // 共三點
100 100 // 第1點座標(x, y) = (100, 100)
200 100 // 第2點座標(x, y) = (200, 100)
300 200 // 第3點座標(x, y) = (300, 200)
0 // 檔案結尾
```
輸出格式：  
分為「點」和「線段」：  
點座標(x, y)  
線段為兩個端點A(x, y),B(x, y)的座標  

```
P 100 100 // 點 (100, 100)
P 200 100 // 點 (200, 100)
P 300 200 // 點 (300, 200)
E 0 550 150 250 // 線段 A(  0, 550); B(150, 250)
E 150 0 150 250 // 線段 A(150,   0); B(150, 250)
E 150 250 400 0 // 線段 A(150, 250); B(400,   0)

```
## 軟體說明
執行 VoronoiDiagramWPF.exe

## 測試
可用滑鼠直接點擊，或以輸入test file，以獲得測試資料。  
並以Step按鈕，檢視Voronoi Diagram是否正確，以進行軟體測試。  
測試資料:https://par.cse.nsysu.edu.tw/~cbyang/course/algo/vd_testdata_pure.in

## 步驟
![](https://raw.githubusercontent.com/lsps9150125/Vonoroi/main/step1.JPG)
![](https://raw.githubusercontent.com/lsps9150125/Vonoroi/main/step2.JPG)
![](https://raw.githubusercontent.com/lsps9150125/Vonoroi/main/step3.JPG)
![](https://raw.githubusercontent.com/lsps9150125/Vonoroi/main/step4.JPG)
![](https://raw.githubusercontent.com/lsps9150125/Vonoroi/main/step5.JPG)
![](https://raw.githubusercontent.com/lsps9150125/Vonoroi/main/step6.JPG)
![](https://raw.githubusercontent.com/lsps9150125/Vonoroi/main/step7.JPG)
![](https://raw.githubusercontent.com/lsps9150125/Vonoroi/main/run.JPG)

## 資料結構
Point: 儲存點座標(x,y)及處理相關運算。  
Edge: 儲存線段(兩個點座標)及處理相關運算。  
Vector: 處理向量相關運算，如：內積、外積、順時針或逆時針旋轉。  
Triangle: 處理三角形相關運算，如：三點外心、三角形面積(判斷是否共線、共點)。   
ConvexHull: 儲存Voronoi Diagram之ConvexHull及相關運算。  
Voronoi:儲存上述所有data。  

## 結論與心得
輸入點在7以上，可能會有多餘的線段未被削去，常出現在鈍角三角形的convex hull上長邊的中垂線。
