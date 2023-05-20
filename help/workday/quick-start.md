---
title: Workday 快速入門手冊
description: 想要在 Workday 環境中使用Adobe Sign的客戶快速入門手冊。
uuid: 10bf8ee8-9075-44d1-a836-e454950e2d9a
products: Adobe Sign
content-type: reference
discoiquuid: 13135c88-4c39-4707-b7ba-63ff94769258
locnotes: All languages; screenshots to follow what's there already (seems there is a mix within a given language version of the article)
type: Documentation
solution: Acrobat Sign
role: User, Developer
topic: Integrations
exl-id: 8b6fa8b4-e240-4ebe-ae2a-8807d75a6c69
source-git-commit: 2cc0ea55ee7dca3682896c61c85eec29a555339c
workflow-type: tm+mt
source-wordcount: '1347'
ht-degree: 0%

---

# [!DNL Workday] 快速入門手冊{#workday-quick-start-guide}

[**連絡Adobe Sign支援人員**](https://www.adobe.com/go/adobesign-support-center)

## 概述 {#overview}

本檔旨在協助 [!DNL Workday] 管理員瞭解如何自訂業務流程， [!DNL Workday] 以納入Adobe Sign以取得電子簽名。 若要在應用程式內 [!DNL Workday] 使用Adobe Sign，您必須瞭解如何建立和修改 [!DNL Workday] 專案，例如：

* [!UICONTROL 業務流程框架]
* 租使用者設定和設定
* 報告與 [!DNL Workday] Studio 整合

## 在內部存取Adobe Sign [!DNL Workday] {#access-adobe-sign}

[!UICONTROL Adobe Sign電子簽名功能 ] 會顯示為 [!UICONTROL  「業務流程架構」（BPF） ] 中的「審核檔步驟 ] 」動作 [!UICONTROL  ，並顯示為「分送檔工作」。

## [!UICONTROL 審核檔步驟] {#review-document-step}

[!DNL Workday]「Adobe Sign」會透過 [!UICONTROL  「審核檔」步驟顯示，您可以在其中的 400 多個業務流程中 [!DNL Workday] 新增該步驟 ] ，包括 [!UICONTROL  優惠 ] 、 [!UICONTROL  分發檔和工作 ] 、 [!UICONTROL  賠償 ] 賠償等。

您可以參閱「 [[!DNL Workday]  審核檔步驟 ] ](https://doc.workday.com/#/reader/3DMnG~27o049IYFWETFtTQ/TboWWKQemecNipWgxLAjqg) 」上的 [!UICONTROL  社群文章。

「審核檔步驟 ] 」與含 Adobe Sign 的 ] 可計費交易之間 [!UICONTROL [!UICONTROL  有一對一關聯性。您可以在單 [!UICONTROL  一「審核檔」步驟 ] 中合併多份檔，這些檔會顯示為單一套件以供簽署。

**注意** ：只能在特定 [!UICONTROL  「審核檔」步驟中參照單 *一「動態* 檔」 ] 。

若要定義功能性 [!UICONTROL  「審核檔」步驟 ] ：

1. 插入審核 [!UICONTROL  檔步驟 ] 。
1. 指定可依「審核檔」步驟 ] 操作的 [!UICONTROL  群組 （角色）。

![業務流程步驟](images/insert-review-doc-steptornm-575.png)

若要設定「 [!UICONTROL  審核檔」步驟 ] ：

1. *[!UICONTROL 依Adobe]* 將電子簽名整合類型 ]*指定為*[!UICONTROL  eSign。

1. 將列新增至「簽名格點」。

   * 簽名格點會指定傳送檔進行簽署的序號順序。 每一列都可包含一或多個角色，每一列代表簽署程式中的步驟。
   * 在特定步驟中，每個角色的成員都會收到通知，表示有待處理的簽署事件。
   * 角色中單一人員簽署後，列步驟就會完成，檔會移至下一列步驟。
   * 所有列都已簽署後，「 [!UICONTROL  審核檔」步驟 ] 即完成。

1. 指定要簽署的檔。 如果檔為 Offer [!UICONTROL  BP ] ，您可以透過「產生檔」步驟加以使用。 否則，請選擇現有的檔或報告。

1. 針對所需的檔重複步驟 3。

   ![設定審核檔步驟](images/configure-rd-stepsmaller-575.png)

1. 您也可以選擇新增「重新導向使用者」，以擷取「拒絕簽署」動作。 當使用者拒絕時， [!DNL Workday] 請將檔重新傳送至已設定的安全群組以供審核。

從「審核檔步驟」的 [!UICONTROL  相關動作選單中，選取 **[!UICONTROL 「業務流程]** 」> **[!UICONTROL 「維持重新導向」]** 。 ]接著，選取下列其中一項：

* **[!UICONTROL 「返回]** 」：若要讓安全群組成員退回業務流程中的上一步。 業務流程會從該步驟重新開機。
* **[!UICONTROL 移至下一步]** ：讓安全群組成員可以前進到業務流程的下一步。
* **[!UICONTROL 安全群組]** ：以重新導向業務流程中的步驟。 「重新導向」區段的業務流程安全性原則中選取此提示顯示的安全群組。

## 業務流程步驟說明 {#business-process-step-notes}

業務 [!UICONTROL  流程框架 ] 功能強大，但您必須確保：

* 每個業務流程都必須有一個完成步驟，最好是在業務流程結束時完成。

* 搜尋圖示的相關動作選單會設定完成步驟。 只有在「檢視」BP（而非「編輯」BP） 時才可以這樣做。

* 業務流程的每個步驟都會依序執行。

   您可以變更訂單值來變更步驟的順序。 例如，若要在專案「c」和「d」之間插入一個步驟，請將新專案指定為「ca」。

### 範例：優惠 {#example-offer}

Offer BP 是 Job Application Dynamic BP ] 的 [!UICONTROL  副程式，必須設定為執行 Offer BP。當工作應用程式狀態移至「 [!UICONTROL  優惠 ] 」或「 [!UICONTROL  優惠」時，將會觸發此設定 ] 。

以下範例中， [!UICONTROL  「審核檔」步驟 ] 是使用北美和日本的「動態檔」步驟。

![業務流程范 [!DNL Workday] 例](images/bp-for-offersmaller-575.png)

此 BP 執行下列作業：

* 要求 BP 的召集者要求要求對應聘者進行補償 （步驟 b）。
* 使用步驟條件測試目前的國家/地區是否不是日本。

   若為 true，則會執行使用英文檔的步驟 「ba」。

   若為 false，則會執行使用日文檔的步驟「bb」。

* 在「審核檔」步驟 ] 「bc」中 [!UICONTROL  定義簽名程式。
* 定義在必要完成步驟「d」中提供優惠的決策點。

在步驟「ba」中產生的動態檔稱為 Offer [!UICONTROL  Letter ] ，並包含名為 Rapid Offer ] 的 [!UICONTROL  單一文字區塊。您可以視需要新增多個文字區塊，例如頁首、標記、補償、Stock、結案、條款等。

![[!DNL Workday] 檢視檔頁面](images/offer-letter-575.png)

以下動態聘書是在 RTF 文字編輯器中 [!DNL Workday] 建立的。 以灰色標示 *的專案是 [!DNL Workday] 參考上下文資料的* 物件。

專案Adobe {{brackets}} [ 文字標籤。 ](https://adobe.com/go/adobesign_text_tag_guide)

![動態表格範例](images/script.png)

在「 [!UICONTROL  審核檔」步驟 ] 中，系統會參考上一個步驟中的動態檔，並透過兩個簽署群組定義連續的簽名程式。

以下說明的行為會先將動態產生的檔傳送給雇用管理員，然後路由至應徵者。

![[!DNL Workday] 定義的簽署群組](images/configure-rd-stepsmaller-575.png)

### 範例：分發檔 {#example-distribute-documents}

在 [!DNL Workday] 30 天內推出「大量分送檔或工作」工作，可用來將單一檔傳送給大量群組 （&lt;20K) of individual signers. 每份檔僅限一個簽名。 從搜尋列存取「 [!UICONTROL  建立分送檔或工作 ] 」動作，以建立分送。

範例：傳送員工股票選擇表格給使用 Global Modern Services ] 的所有經理 [!UICONTROL  。您可以視需要進一步篩選給個別經理。

您也可以存取「 **檢視分送檔或工作** 」報告，追蹤分送進度。

![](images/create-distributedocumentsortasks.png)

### 範例：報告 {#example-reporting}

[!DNL Workday] 擁有豐富的報告基礎架構。 若要查看Adobe Sign程式的詳細資訊，請檢查「審核檔事件 *」的* 元素。

以下是可在所有尋找Adobe Sign交易及其狀態的 BP 中執行的簡單自訂報告。

![自訂報告范 [!DNL Workday] 例](images/review-document-eventsmaller-575.png)

下列報告是透過檢視實施租使用者中的優惠、Onboarding 和就地補償 BP 所產生。

您可以看到：

* 送出供簽署的檔
* 關聯的 BP 步驟
* 下一個需要簽名的人

![使用三個 [!DNL Workday] 物件的報告範例](images/workday-reportsmaller-575.png)

## 已簽署的檔 {#signed-documents}

簽署週期會 [!DNL Workday] 透過Adobe Sign來隱藏所有電子郵件通知。 使用者會在其收件匣中 [!DNL Workday] 得知待處理的動作。

一旦所有「簽名群組」簽署檔，已簽署檔的副本便會透過電子郵件分發給「簽名群組」的所有成員。

若要抑制此行為，您可以聯絡您的 [!UICONTROL  Adobe Sign Success Manager ] 或 [ Adobe Sign 支援小組 ](https://adobe.com/go/adobesign-support-center) 。

在內部 [!DNL Workday] ，您可以在完整程式記錄中存取已簽署的檔。 您可能會發現：

* 在「員工基本資料」上處理員工檔，以及
* 應聘者個人資料上的應聘者檔 （錄用信函）。

下圖顯示求職者 Chris Foxx 的已簽署錄用通知。

![範例 [!DNL Workday] 錄取通知](images/offer.png)

## 支援 {#support}

### [!DNL Workday] 支援 {#workday-support}

[!DNL Workday] 是整合擁有者，對於整合的範圍、功能要求或整合日常功能的問題，應成為您的第一個聯絡點。

社 [!DNL Workday] 群提供數篇好文章，說明如何疑難排解整合及產生檔：

* [電子簽名整合疑難排解](https://doc.workday.com/#/reader/3DMnG~27o049IYFWETFtTQ/zhA~hYllD3Hv1wu0CvHH_g)
* [審核檔步驟](https://doc.workday.com/#/reader/3DMnG~27o049IYFWETFtTQ/TboWWKQemecNipWgxLAjqg)
* [動態檔產生](https://community.workday.com/node/176443)
* [提供檔產生設定提示](https://community.workday.com/node/183242)

### Adobe Sign支援 {#adobe-sign-support}

Adobe Sign是整合合作夥伴，如果整合無法取得簽名，或有擱置中簽名的通知失敗，請連絡此人。

Adobe Sign客戶應聯絡其 [!UICONTROL  客戶成功經理 ] 尋求支援。 或者， [!UICONTROL  您也可以透過電話連絡Adobe技術支援 ] ：1-866-318-4100，等候產品清單然後輸入：4 和 2 （依提示操作）。

* [將Adobe文字標籤新增至檔](https://www.adobe.com/go/adobesign_text_tag_guide)

<!--
[Download PDF](images/adobe-sign-for-workday-quick-start-guide-2016.pdf)
-->
