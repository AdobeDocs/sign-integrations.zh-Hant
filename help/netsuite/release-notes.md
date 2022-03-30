---
title: Adobe Sign for NetSuite 發行說明
description: 瞭解最新版 Adobe Sign NetSuite 整合中所包含的新功能和變更。
type: Documentation
solution: Acrobat Sign
role: User, Developer
topic: Integrations
exl-id: 6317723e-447a-4506-a621-4d967bdd6561
source-git-commit: 4d73ff36408283805386bd3266b683bc187d6031
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 51%

---

# Adobe Sign for NetSuite 發行說明

## 套件 4.0.4 版的更新

4.0.4 版適用於針對全新產生的流量使用帳戶專屬網域。

Adobe Sign 圖示已更新為新圖形。

## 舊版

### Adobe Sign for NetSuite 4.0.4

4.0.4 版適用於針對全新產生的流量使用帳戶專屬網域。

Adobe Sign 圖示已更新為新圖形。

### Adobe Sign for NetSuite 4.0.2

品牌重塑為 **Adobe Sign （從 *Adobe Document Cloud eSign 服務*** ）\
您現在會看到 *先前看到的* Adobe *eSign Services* Adobe Sign，以證明品牌重塑。

### Adobe Sign for NetSuite 4.0.1

NetSuite 更新其平台時造成一個 API 迴歸錯誤，已針對此錯誤發行新套件 (v4.0.1)。

建議客戶更新至最新版套件。

### Adobe Sign for NetSuite 4.0

**新增透過 NetSuite 自動佈建使用者的功能**

已針對 4.0 版新增新的自訂偏好設定。啟用後，在 NetSuite 中傳送合約的使用者會自動布建 Adobe Document Cloud eSign 服務使用者帳戶。

**經「Built for NetSuite」認證**

此版本獲得「Built for NetSuite」認證，符合所有最新的 NetSuite 設計最佳做法。

**品牌重塑後更名為 Adobe Document Cloud eSign 服務 (舊稱為 EchoSign)**

您現在看到先前看到的 Adobe Document Cloud eSign Services （或簡稱 Adobe eSign Services） Adobe EchoSign，作為品牌重塑的證據。

**透過 OAuth 實作強化安全性**

為了提高資料安全性，eSign 服務現在使用 OAuth 2.0 來驗證 NetSuite 內的 Adobe Document Cloud eSign 服務帳戶。 這個新的通訊協定讓 NetSuite 能與 eSign 服務通訊，無須要求您提供 eSign 服務密碼。敏感資訊不會直接在應用程式之間共用，因此降低了帳戶遭盜用的可能性。此改良功能不會影響您的實作，但您必須進行一次性設定，授權您的 NetSuite 套件以與Adobe Document Cloud通訊。 此步驟會在安裝過程中完成。針對從舊版套件 （v3.5.9 和更早版本） 升級的客戶，先前使用的API金鑰會取代為授權過程中產生的 OAuth 權杖。

**將 eSign 服務從 SOAP API 移轉至 REST API**

為了提高效率、彈性和處理速度，Adobe Document Cloud eSign 服務，因此適用于 NetSuite 的 v4.0 整合已從 SOAP 型移轉至基於 REST 的 API。

### Adobe Sign for NetSuite 3.0

**進階參與者角色 - 核准者**

* 一份合約中可將一或多位收件者標示為核准者
* 核准者必須審閱及核准檔
* 核准者也可能需在核准前將資料填入合約中

**傳送前預覽文件或拖放表單欄位**

傳送以供簽署前預覽合約或拖放表單欄位

**傳送提醒給目前的簽署者**

立即傳送提醒給目前的簽署者

**進階簽署者Authentication政策**

* **知識型Authentication：** 回答問題以驗證簽署者身分
   * 要求簽署者回答從數百個公開和商業資料庫汲取的問題以證明其身分
   * 簽名的姓名需取自使用者通過驗證的姓名，且簽署時不能更改
   * RSA 提供技術支援
   * KBA 的使用限制為按帳戶、按月計價。如需詳細資訊，請連絡銷售人員。

* **網頁身分：** 簽署前請先使用 Facebook、LinkedIn、Google 或其他協力廠商網頁服務登入。

   * 簽署者使用第三方 Web 服務驗證其身分後才能簽署.
   * 簽名的姓名需取自使用者的 Web 服務個人檔案，且簽署時不能更改
   * 稽核記錄擷取了身分驗證詳細資訊

* **一次性密碼**
   * 為內部或外部簽署者或是所有簽署者套用驗證方法。外部簽署者必須使用密碼或知識式Authentication，而內部簽署者則不

**其他自訂偏好設定**

* 將已簽署的 PDF 新增為URL連結，或新增為在 NetSuite 中託管的附件
* 合約簽署後將稽核記錄新增至合約記錄中
* 依預設，使用交易連絡人作為簽署者，而非客戶電子郵件
* 為傳送者提供將收件者標示為核准者的選項

**交易檔案**

您可以使用新的「交易檔案」下拉式清單，從目前交易中選取要附加的檔案。

**所有 EchoSign 文件適用的 Adobe PDF 認證**

* 所有從 EchoSign 傳送或下載的 PDF 檔案都會通過Adobe EchoSign數位憑證認證
* Acrobat或 Reader 顯示保證檔未經過竄改以獲得額外信任及安心的認證

**收集支援文件**

* 傳送者可以在簽署期間向簽署者收取其他證明檔，例如駕照、商業證書等。
* 收取的文件會成為已簽署合約官方記錄的一部分

**條件式資料欄位**

* 為合約欄位定義條件式邏輯
* 條件能以合約中一或多個欄位的值為依據
* 可透過拖放式表單編寫 UI 或透過文字標籤來定義條件
* 簽署檔時，會根據已取消設定的條件向簽署者顯示適當的欄位

**額外 EchoSign 表單欄位增強功能**

* 下拉式選單
* 欄位遮罩
* 選項按鈕
* 建立較短的文字標籤以維持文件結構
