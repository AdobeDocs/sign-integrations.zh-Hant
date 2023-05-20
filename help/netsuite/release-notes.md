---
title: Adobe Sign for NetSuite 版本資訊
description: 瞭解最新版 Adobe Sign NetSuite 整合中所包含的新功能和變更。
type: Documentation
solution: Acrobat Sign
role: User, Developer
topic: Integrations
exl-id: 6317723e-447a-4506-a621-4d967bdd6561
source-git-commit: 4d73ff36408283805386bd3266b683bc187d6031
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 0%

---

# Adobe Sign for NetSuite 版本資訊

## 套件 4.0.4 版的更新

4.0.4 版完全適合針對新產生的流量使用帳戶專屬網域。

Adobe Sign圖示已更新為新圖形。

## 舊版

### 適用于 NetSuite 4.0.4 的Adobe Sign

4.0.4 版完全適合針對新產生的流量使用帳戶專屬網域。

Adobe Sign圖示已更新為新圖形。

### 適用于 NetSuite 4.0.2 的Adobe Sign

品牌重塑為 **Adobe Sign （從 *Adobe Document Cloud eSign 服務*** ）\
您現在會看到 *先前看到的* Adobe *eSign Services* Adobe Sign，以證明品牌重塑。

### 適用于 NetSuite 4.0.1 的Adobe Sign

NetSuite 更新其平臺時，由於API回歸錯誤，已發行新套件 （v4.0.1）。

建議客戶更新至最新套件。

### 適用于 NetSuite 4.0 的 Adobe Sign

**新增透過 NetSuite 自動布建使用者的功能**

已針對 4.0 版新增新的自訂偏好設定。啟用後，在 NetSuite 中傳送合約的使用者會自動布建 Adobe Document Cloud eSign 服務使用者帳戶。

**經「Built for NetSuite」認證**

此版本獲得「Built for NetSuite」認證，符合所有最新的 NetSuite 設計最佳做法。

**品牌重塑後更名為 Adobe Document Cloud eSign 服務 （來自 EchoSign）**

您現在看到先前看到的 Adobe Document Cloud eSign Services （或簡稱 Adobe eSign Services） Adobe EchoSign，作為品牌重塑的證據。

**透過 OAuth 實作增強安全性**

為了提高資料安全性，eSign 服務現在使用 OAuth 2.0 來驗證 NetSuite 內的 Adobe Document Cloud eSign 服務帳戶。 這個新的通訊協定讓 NetSuite 無需索取 eSign 服務密碼即可與 eSign 服務對話。 由於敏感資訊不會直接在應用程式之間共用，因此降低了帳戶遭洩露的可能性。 此改良功能不會影響您的實作，但您必須進行一次性設定，授權您的 NetSuite 套件以與Adobe Document Cloud通訊。 這會在安裝過程中完成。 針對從舊版套件 （v3.5.9 和更早版本） 升級的客戶，先前使用的API金鑰會取代為授權過程中產生的 OAuth 權杖。

**將 eSign 服務從 SOAP API 移轉至 REST API**

為了提高效率、彈性和處理速度，eSign 服務Adobe Document Cloud，因此 NetSuite 的 v4.0 整合已從 SOAP 型移轉至基於 REST 的 API。

### 適用于 NetSuite 3.0 的Adobe Sign

**進階參與者角色 - 核准者**

* 一份合約可將一或多位收件者標示為核准者
* 核准者必須審閱及核准檔
* 核准者也可能需要在核准前將資料填入合約中

**傳送前預覽檔或拖放表單欄位**

傳送以供簽署前預覽合約或拖放表單欄位

**傳送提醒給目前的簽署者**

立即傳送提醒給目前的簽署者

**進階簽署者Authentication政策**

* **知識型Authentication：** 回答問題以驗證簽署者身分
   * 要求籤署者回答從數百個公開和商務資料庫拍攝的問題以證明其身分
   * 簽名的名稱需取自使用者通過驗證的名稱，且簽署時不能變更
   * 由 RSA 提供技術支援
   * KBA 的使用限制為按帳戶、按月使用。 如需詳細資訊，請聯絡銷售人員。

* **網頁身分：** 簽署前請先使用 Facebook、LinkedIn、Google 或其他協力廠商網頁服務登入。

   * 簽署者只能在使用協力廠商 Web 服務驗證其身分後進行簽署。
   * 簽名的名稱需取自使用者的 Web 服務 pro！le，且簽署時不能變更
   * 稽核記錄擷取身分驗證詳細資料

* **一次性密碼**
   * 為內部或外部簽署者或所有簽署者套用驗證方法。 外部簽署者必須使用密碼或知識式Authentication，而內部簽署者則不

**其他自訂偏好設定**

* 將已簽署的 PDF 新增為URL連結，或新增為在 NetSuite 中託管的附件
* 合約完成簽署後，將稽核記錄新增至合約記錄中
* 依預設，使用交易連絡人作為簽署者，而非客戶電子郵件
* 為傳送者提供將收件者標記為核准者的選項

**交易檔案**

您可以使用新的「交易檔案」下拉式清單，從目前交易中選取要附加的檔案。

**所有 EchoSign 檔Adobe PDF認證**

* 所有從 EchoSign 傳送或下載的 PDF 檔案都會通過Adobe EchoSign數位憑證認證
* Acrobat或 Reader 顯示保證檔未經過竄改以獲得額外信任及安心的認證

**收集證明檔**

* 傳送者可以在簽署期間向簽署者收取其他證明檔，例如駕照、商業證書等。
* 收集的檔會成為已簽署合約官方記錄的一部分

**條件式資料欄位**

* 為合約欄位定義條件式邏輯
* 條件可根據合約中一或多個欄位的值
* 可透過拖放表單編寫UI或透過文字標籤來定義條件
* 簽署檔時，會根據已取消設定的條件向簽署者顯示適當的欄位

**其他 EchoSign 表單欄位增強功能**

* 下拉式選單
* 欄位遮色片
* 選項按鈕
* 建立較短的文字標籤以維持檔結構
