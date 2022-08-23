# AEC - Acoustic Echo Cancelling

## What's AEC ?
+ 回音消除
+ 透過`音波干擾`的方式消除自身回傳的聲音
+ 回音由來：用戶A的聲音透過用戶B的喇叭播出，再經用戶B麥克風回傳，導致用戶A會聽見延遲的自身聲音，造成干擾

## 聲學迴聲消除器

![image](https://github.com/kohsin520/AEC-/blob/main/v2-15cce9ef1dcc1366be298b94aaba87f7_1440w.jpeg)

+ 估計本地揚聲器到本地麥克風的聲學傳輸函數 (包含反射路徑)
1. 通過估計的聲學傳輸函數過濾傳入的語音信號，得到圖1中估計的回聲`y(n)`
2. 麥克風信號`d(n)`減去估計的迴聲`y(n)`，得到無迴聲的信號`e(n)`，`e(n)=d(n)-y(n)`
3. 將信號`e(n)`通過信道傳輸到遠端。若估計的y(n)是準確的，就可以`完全消除迴聲`


## REFERENCE
+ [什麼是AEC聲學迴聲消除器？](https://zhuanlan.zhihu.com/p/182436289?fbclid=IwAR1J-U7YYdukOpghQH1-BRL6mt763R9hhD_ICUPaQlaO7G_N1TljmCn6-0c)
+ 
