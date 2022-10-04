# AEC - Acoustic Echo Cancelling

## What's AEC?
+ 回音消除
+ 透過`音波干擾`的方式消除自身回傳的聲音
+ 當source所發出的聲音，經過一段時間的延遲後，反射回source，且其能量大到足夠讓使用者察覺，就會產生回音；例如，當使用者使用免持模式時，由喇叭放出的聲音及其反射之後的訊號，會被麥克風所捕捉，形成回音。
+ 回音對使用者造成的影響取決於回音的`強度`及`延遲`；當回音的強度太小，使用者無法察覺；當回音的延遲太短，使用者亦無法分辨出來。

## 聲學迴聲消除器(Echo Canceller)

回音消除器的精神在於`模擬出回音路徑(Echo Path)的空間模型(impulse response)`，依據此模型，計算出遠端訊號(Far-End Signal)透過喇叭放出，經過空間，由麥克風捕捉後所會產生的回音，並將麥克風實際所收到的聲音減去此計算出來的回音；如果模擬的模型夠精準，使得計算出來的回音與實際的回音一樣的話，最後送出的聲音即可將回音消除，但不影響近端使用者所發出的聲音。

![image](https://github.com/kohsin520/AEC-/blob/main/v2-15cce9ef1dcc1366be298b94aaba87f7_1440w.jpeg)

+ 估計本地揚聲器到本地麥克風的聲學傳輸函數 (包含反射路徑)
1. 通過估計的聲學傳輸函數過濾傳入的語音信號，得到圖1中估計的回聲`y(n)`
2. 麥克風信號`d(n)`減去估計的迴聲`y(n)`，得到無迴聲的信號`e(n)`，`e(n)=d(n)-y(n)`
3. 將信號`e(n)`通過信道傳輸到遠端。若估計的y(n)是準確的，就可以`完全消除迴聲`。


## REFERENCE
+ [什麼是AEC聲學迴聲消除器？](https://zhuanlan.zhihu.com/p/182436289?fbclid=IwAR1J-U7YYdukOpghQH1-BRL6mt763R9hhD_ICUPaQlaO7G_N1TljmCn6-0c)
+ [Echo Cancellation](http://joseph0425.blogspot.com/2007/05/echo-cancellation.html)
