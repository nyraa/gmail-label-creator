# 簡述
專為成功大學的Google Suite Email服務建立標籤的Script（適當小修改後可以通用到其他地方）  
學校寄來的公告email全部雜亂在一起看起來很中風，此Google App Script可以依寄件者（單位處室）自動新增Gmail的Label跟Filter以歸類學校公告信件。  
此Script運作的前提在於可以先用過濾器一次過濾出全部公告並標上公告標籤以辨識需要自動分類的郵件，例如此情況是公告統一由no-reply@mail.ncku.edu.tw寄出

## 使用說明
1. 建立一份此[GAS](https://script.google.com/d/1qbvvdGtI5CiiZcUPqwyXTnuff4L8QQFQdhY-0yHCDWUcBV_19shVjlCG/edit?usp=sharing)的副本到自己學校帳號下
2. 建立Email篩選器，將寄件者是學校公告用的no-reply@mail.ncku.edu.tw自動標上「公告」標籤，並套用到現有所有郵件
3. 在此`main.gs`檔案第一個字串中指定公告標籤名稱
4. 在左側「觸發條件」中新增觸發`process_email`的定時條件，建議數小時至一天觸發一次即可
5. 在編輯器中`main.gs`檔案手動執行一次`process_email`函數來把現存的郵件歸類並自動新增篩選器，同時授予權限

## 截圖
![](https://github.com/nyraa/gmail-label-creator/blob/master/screenshot_1.png?raw=true)
圖中左方全部的標籤都是自動產生的，對應的篩選器設定也會自動生成

## 不知道標題要打什麼了
有bug歡迎回報

## 已知問題
Gmail的filter是關鍵字符合就會篩過，所以如「圖書館」標籤會符合寄件者為「圖書館」與「圖書館知服組」與「圖書館知識服務組」

## 更新紀錄
因為GAS不能匯出入檔案，故要手動將更新的gs檔貼上自己的專案。
* 2022/9/12：  
修復寄件備份會造成的例外。  
已修改檔案：`main.gs`