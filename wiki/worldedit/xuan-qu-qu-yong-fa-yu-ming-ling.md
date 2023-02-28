---
description: >-
  WorldEdit 的一個最基本的部分是使用選區取進行的操作。舉個例子，如果你想把一個長方體區域內的草方塊換成泥土，你需要告訴 WorldEdit
  這個長方體區域的位置。WorldEdit 提供了多種區域樣式與方法，這個部分將會向你介紹各種選取區，與選取方法。
---

# 選取區用法與命令

{% hint style="info" %}
本網頁的教學可能會包含更進階的 FastAsyncWorldEdit
{% endhint %}

> **`<>` 內的代表一定要填寫，`[]` 內的則不一定**

## 選擇選區 <a href="#xuan-ze-xuan-ou" id="xuan-ze-xuan-ou"></a>

WorldEdit允許你以選擇長方體的兩個角上的點的方式來選擇長方體（想像一個3D的長方體）。\
下方的圖展示瞭如何用兩點形成一個長方體。你選擇的長方體是與 Minecraft 方塊對齊的。\


<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption><p>長方體選取區式意圖</p></figcaption></figure>

有許多方法可以用來選擇這兩個點，你可以混合使用這些方法。

### 第一種方法：用木斧選取

先打 `//wand` 命令獲取木斧，然後分別用左、右鍵選擇端點。(左鍵為第一點，右鍵為第二或更多點)

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption><p>在長方體選取模式下的選取</p></figcaption></figure>

### 第二種方法，**選擇你的目前站著的位置或座標( `//pos1`、`//pos2` )**

* `//pos1 [x,y,z]` 選取第一點。(座標非必填)
* `//pos2 [x,y,z]` 選取第二點。(座標非必填)

使用這些指令(沒填座標時)可以將**你所站的**方塊上方一個方塊的位置分別設定為第一個和第二個角。添加指定坐標，則選取指定坐標點。

### **選擇十字準星指向的位置( `//hpos1`、`//hpos2` )** <a href="#xuan-ze-shi-zi-zhun-xing-zhi-xiang-de-wei-zhi-hpos1hpos2" id="xuan-ze-shi-zi-zhun-xing-zhi-xiang-de-wei-zhi-hpos1hpos2"></a>

* `//hpos1` 選取第一點。
* `//hpos2` 選取第二點。

這兩個指令會將你十字準星所指的位置分別設置為第一個和第二個頂點。通過這個方式可以選擇遠處的點以及方便地選擇非常大的選區。

### **選擇所在區塊( `//chunk` )**

* `//chunk`

這個命令會選擇你所站區塊的所有方塊。區塊是16x16, 從最底到最高的範圍。

## 調整選區 <a href="#diao-zheng-xuan-ou" id="diao-zheng-xuan-ou"></a>

### **縮小選區（`//contract`）** 留言 <a href="#su-xiao-xuan-ou-contract" id="su-xiao-xuan-ou-contract"></a>

* `//contract <數量> [反方向數量] [方向]`

這個指令與`//expand`類似。

**例子：向下收縮**

使用`//contract 10 down`將選區會從上往下進行收縮。

![](https://i.imgur.com/sxXhptV.png)

### **移動選區位置**(`//shift`) <a href="#yi-dong-xuan-ou-wei-zhi-shift" id="yi-dong-xuan-ou-wei-zhi-shift"></a>

* `//shift`

移動選區。這個指令的效果類似與向兩個相反方向分別進行相同移動量的`//expand`與`//contract`。如此會將選區移動一段距離。這個命令不會移動選區中的內容。（如果要達到該效果需要使用`//move`指令，如需同時移動選區內容和位置，可以給`//move`添加`-s`。）

### **在各軸同時擴張（`//outset`）** <a href="#zai-ge-zhou-tong-shi-kuo-zhang-outset" id="zai-ge-zhou-tong-shi-kuo-zhang-outset"></a>

這個指令會將選區向外縮擴張。

* `//outset <數量> [-hv]`
* `-h`表示只水平方向上（horizonally）擴張。
* `-v`表示只豎直方向上（vertically）擴張。

### **在各軸同時收縮（`//inset`）** <a href="#zai-ge-zhou-tong-shi-shou-su-inset" id="zai-ge-zhou-tong-shi-shou-su-inset"></a>

這個命令會將選區向內縮小。

* `//inset <數量> [-hv]`
* `-h`表示只水平方向上（horizonally）收縮。
* `-v`表示只豎直方向上（vertically）收縮。

### **擴展選區（`//expand`）** <a href="#kuo-zhan-xuan-ou-expand" id="kuo-zhan-xuan-ou-expand"></a>

* `//expand <數量> [反方向數量] [方向]`
* `//expand vert`

這些指令可以簡單地以許多方式擴大選區:

* 給出一個方向（`north`、`south`、`west`、`east`、`up`、`down`）
* 看向一個方向（`me`、`back`）

擴大選區到基岩和天空\
如果你想選擇看向的一個方向，使用`me`或不輸入方向參數來指定那個方向，也可以用`back`表示與看向的方向相反的方向。

你可以指定兩個數字來使選區同時向兩個方向擴大選區。使用`//expand vert`可以將選區豎直方向擴展到整個世界的限度。

例子：向上收縮\
使用`//expand 10 up`將選區向上擴大\
如圖，選區向上擴大\


<figure><img src="https://i.imgur.com/4PgkzSO.png" alt=""><figcaption></figcaption></figure>

## 選區訊息 <a href="#xuan-ou-xun-xi" id="xuan-ou-xun-xi"></a>

> WorldEdit提供了一些可以得到選擇的區域的訊息的命令。

### **獲得選區尺寸（`//size`）** <a href="#huo-de-xuan-ou-chi-cun-size" id="huo-de-xuan-ou-chi-cun-size"></a>

* `//size [-c]`

顯示選區內的方塊數量。空氣方塊不會被計算。

使用`-c`標簽會對剪貼板進行計算

### **獲取一種方塊的數量（`//count`）** <a href="#huo-qu-yi-zhong-fang-kuai-de-shu-liang-count" id="huo-qu-yi-zhong-fang-kuai-de-shu-liang-count"></a>

* `//count <方塊種類>`\
  顯示一種指定方塊在選區內的數量。
* 使用`-d`標簽可以支持不同附加值的方塊。注意使用`-d`標籤是需要給出一個附加值。

### **獲取方塊分布率（`//distr`）** <a href="#huo-qu-fang-kuai-fen-bu-lv-distr" id="huo-qu-fang-kuai-fen-bu-lv-distr"></a>

* `//distr [-cd] [-p <頁面>]`\
  使用`-c`會對剪貼板內容進行計算。\
  使用`-d`會對不同狀態的方塊進行區分。\
  顯示選區內的方塊分布。

## 切換選區模式  <a href="#qie-huan-xuan-ou-mo-shi" id="qie-huan-xuan-ou-mo-shi"></a>

> 除了預設的長方體選取區模式，WorldEdit也有不同的選取模式可供選擇。\
> 可用`//sel -d <選區模式>`來更改預設選區模式。

### **長方體選擇模式（`//sel cuboid`）** <a href="#chang-fang-ti-xuan-ze-mo-shi-selcuboid" id="chang-fang-ti-xuan-ze-mo-shi-selcuboid"></a>

* `//sel cuboid`\
  左鍵點擊選擇第一個點，右鍵點擊選擇第二個點。選區為兩個點形成的長方體。

選擇對角來選擇長方形區域

<figure><img src="https://i.imgur.com/rr5ShK4.png" alt=""><figcaption></figcaption></figure>

### **長方體擴大選擇模式（`//sel extend`）** <a href="#chang-fang-ti-kuo-da-xuan-ze-mo-shi-selextend" id="chang-fang-ti-kuo-da-xuan-ze-mo-shi-selextend"></a>

* `//sel extend`\
  左鍵點擊選擇第一個點。之後的選擇點使用右鍵選擇。每次右鍵選擇都會將長方體選區擴大以包含新的選擇點。

### **多邊形選擇模式（`//sel poly`）** <a href="#duo-bian-xing-xuan-ze-mo-shi-selpoly" id="duo-bian-xing-xuan-ze-mo-shi-selpoly"></a>

* `//sel poly`\
  左鍵點擊選擇第一個選擇點。之後所有的選擇點使用右鍵點擊。每次右鍵點擊選擇都會增加一個新的點。頂部和底部將始終包含所選的最高點和最低點。

三點

\


<figure><img src="https://i.imgur.com/IdeoDa6.png" alt=""><figcaption></figcaption></figure>

### **橢球選擇模式（`//sel ellispoid`）** <a href="#tuo-qiu-xuan-ze-mo-shi-selellispoid" id="tuo-qiu-xuan-ze-mo-shi-selellispoid"></a>

* `//sel ellipsoid`\
  左鍵點擊選擇圓心，右鍵點擊擴大選區。你可以通過分別多次點擊以控制x、y、z半徑。

#### 平面橢圓需要有**三**個點(圓心、長、寬)  結果： 

<figure><img src="https://i.imgur.com/2vdPGlF.png" alt=""><figcaption></figcaption></figure>



<figure><img src="https://i.imgur.com/geJFkRw.png" alt=""><figcaption></figcaption></figure>

\


立體橢圓需要有**四**個點(圓心、長、寬、高)\
\
結果：\


<figure><img src="https://i.imgur.com/LaCvPZZ.png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://i.imgur.com/hBNNu8z.png" alt=""><figcaption></figcaption></figure>

### **球體選擇模式（`//sel sphere`）** <a href="#qiu-ti-xuan-ze-mo-shi-selsphere" id="qiu-ti-xuan-ze-mo-shi-selsphere"></a>

* `//sel sphere`\
  左鍵點擊選擇圓心，右鍵點擊擴大選區。選區總是為以第一個點為圓心、到第二個點作為半徑的一個球體。

### **圓柱體選擇模式（`//sel cyl`）** <a href="#yuan-zhu-ti-xuan-ze-mo-shi-selcyl" id="yuan-zhu-ti-xuan-ze-mo-shi-selcyl"></a>

* `//sel cyl`\
  左鍵點擊選擇圓心，右鍵點擊擴大選區。第一次右鍵點擊可以擴大圓柱體的底面，第二次右鍵點擊可以提升圓柱體的高度。

### **多面體選擇模式（`//sel convex`）** <a href="#duo-mian-ti-xuan-ze-mo-shi-selconvex" id="duo-mian-ti-xuan-ze-mo-shi-selconvex"></a>

* `//sel convex`\
  左鍵點擊選擇第一個點，其餘的點使用右鍵點擊選擇。選區是一個包含所有選定的點的凸面外殼。

三點成面\


<figure><img src="https://i.imgur.com/mu4l0ec.png" alt=""><figcaption></figcaption></figure>

四點成體\


<figure><img src="https://i.imgur.com/NodXtvp.png" alt=""><figcaption></figcaption></figure>
