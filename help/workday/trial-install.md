---
title: Workday 試用版安裝
description: Adobe Sign中試用帳戶的 Workday 安裝指南
uuid: 0c51f329-b7c1-44a2-88a3-670be7673747
products: Adobe Sign
topic-tags: EchoSign/Integrations
content-type: reference
discoiquuid: 63ed2d5b-9d82-4f87-97e1-2dde23501e89
locnotes: All languages; screenshots for Tier 1 and 2 only (see the currently published localized page for guidance)
type: Documentation
solution: Acrobat Sign
role: User, Developer
topic: Integrations
exl-id: beafe6c0-262f-4f5b-9315-a023a4eef4a2
source-git-commit: 4d73ff36408283805386bd3266b683bc187d6031
workflow-type: tm+mt
source-wordcount: '991'
ht-degree: 0%

---

# [!DNL Workday] 試用版安裝{#workday-trial-installation}

## 概述 {#overview}

本檔旨在協助 [!DNL Workday] 客戶瞭解如何使用 Adobe Sign 啟用試用帳戶，然後將其整合至 [!DNL Workday] 租使用者。 若要在應用程式內 [!DNL Workday] 使用Adobe Sign，您必須瞭解如何建立和修改 [!DNL Workday] 專案，例如：

* 業務流程框架
* 租使用者設定和設定
* 報告與 [!DNL Workday] Studio 整合

**注意** ：如果您有現有的 Adobe Sign 帳戶，就不必開始試用。 您可以聯絡客戶成功經理以請求 [!DNL Workday] 整合。

完成整合的高階步驟包括：

* 使用 Adobe Sign 啟用您的試用帳戶
* 在 Adobe Sign 中產生整合金鑰
* 將整合金鑰安裝至 [!DNL Workday] 租使用者

## 啟用您的Adobe Sign試用帳戶 {#activate-sign-trial-account}

若要申請 30 天的 Adobe Sign 試用版，您必須填寫此 [ 註冊表單 ](https://land.echosign.com/esign-trial-workday-registration.html) 。

**注意** ：我們強烈建議您使用有效功能的電子郵件地址來建立試用版，而不是臨時電子郵件。 您必須存取此電子郵件才能驗證帳戶，因此該位址必須有效。

![試用版請求表單](images/trial-land.png)

在一個工作天內，Adobe Sign入門專家會為您的帳戶 （Adobe Sign） 規定 [!DNL Workday] 。 完成後，您會收到確認電子郵件，如下所示。

![來自 Adobe Sign 的歡迎電子郵件](images/welcome-email-2020.png)

若要初始化您的帳戶並存取Adobe Sign [!UICONTROL  首 ] 頁，請依照電子郵件中的指示操作。

![Adobe Sign儀表板](images/classic-home.png)

## 產生整合金鑰 {#generate-an-integration-key}

若要進行新安裝，您必須在 Adobe Sign 產生整合金鑰，然後將其輸入 [!DNL Workday] 。 此金鑰會驗證Adobe Sign與 [!DNL Workday] 環境，以便彼此信任及共用內容。

若要在 Adobe Sign 中產生整合金鑰：

1. 請在 Adobe Sign 中登入您的管理員。
1. 導覽至 **[!UICONTROL **帳戶]** > **[!UICONTROL 個人偏好]** 設定> **[!UICONTROL 存取權杖**]** 。
1. **按一下視窗右側圓圈的加號圖示** 。

   會開啟「 [!UICONTROL  建立整合金鑰 ] 」介面。

   ![導覽至「存取權杖」頁面的影像](images/navigate-to-group-accesstokens.png)

1. 為您的金鑰提供直覺式名稱，例如 [!DNL Workday] 。

   整合金鑰必須啟用下列元素：

   * agreement_read
   * agreement_write
   * agreement_send
   * widget_read
   * library_read

   ![「建立整合金鑰」面板](images/create-integration-key-575.png)

1. 按一下「儲存 **[!UICONTROL 」]** 。

   畫面會 ] 顯示「 [!UICONTROL  存取權杖」頁面，顯示您在帳戶中設計的金鑰。

1. 按一下為 [!DNL Workday] 。

   定義 [!UICONTROL  頂端會顯示「整合金鑰 ] 」連結。

1. 按一下「 **[!UICONTROL 整合金鑰」]** 連結。

   這會顯示整合金鑰。

   ![整合金鑰連結](images/integration-key.png)

1. 複製此金鑰並儲存在安全的位置以執行下一個步驟。
1. 按一下「 **[!UICONTROL 確定」]** 。

   ![「整合金鑰」面板](images/copy-the-key-575.png)

## 設定 [!DNL Workday] 租使用者 {#configuring-the-workday-tenant}

### 安裝整合金鑰 {#install-the-integration-key}

在租使用者中安裝整合金鑰 [!DNL Workday] 可與 Adobe Sign 建立信任關係。 建立關係後，任何業務流程都可以新增「 [!UICONTROL  審核檔」步驟 ] 來啟用簽名程式。

**注意** ：在整個 [!DNL Workday] 環境中，Adobe Sign稱為「Adobe Document Cloud」。

若要安裝整合金鑰：

1. [!DNL Workday]以帳戶管理員的身分登入。
1. Search取並開啟 **[!UICONTROL 「編輯租使用者設定 - 業務流程」]** 頁面。

1. 提供下列四個欄位的資訊：

   * **[!UICONTROL Adobe Document Cloud承認]** ：整合的修正文字辨識。

   * **[!UICONTROL Adobe Document Cloud API金鑰]** ：安裝整合金鑰的位置

   * **[!UICONTROL Adobe Document Cloud寄件者電子郵件地址]** ：Adobe Sign中群組層級管理員的電子郵件地址

   * **[!UICONTROL 「檔已取消]** 」時移除需要電子簽名的檔：如果檔已取消，可選擇性設定，將檔從簽署週期中 [!DNL Workday] 移除。

   ![Adobe Sign整合金鑰的欄位](images/bp-filled-torn2-575.png)

1. 接下來，完成安裝：

   1. 將您的整合金鑰貼Adobe Sign API [!UICONTROL  「整合金鑰」字 ] 段。
   1. 在「傳送者電子郵件地址」欄位中輸入Adobe Sign管理員 [!UICONTROL  的電子郵件地址 ] Adobe Document Cloud。
   1. 按一下「 **[!UICONTROL 確定」]** 。

   ![整合金鑰欄位和關鍵持有人電子郵件欄位](images/bp-filled-small.png)

Adobe Sign功能現在可以新增到任何業務流程中，方法是新增「 [!UICONTROL  審核檔」步驟 ] ，並將其設為透過Adobe ]**作為電子簽名類型來使用**[!UICONTROL  eSign。

### 設定「審核檔」步驟 {#configure-the-review-document-step}

「審核檔」步驟的檔可以是靜態檔;在同一個業務流程中由「產生檔」步驟產生的檔;或是以報告建立的格式化報告 [!DNL Workday] Designer。 所有這些案例都可以使用 [ 「Adobe文字標籤 ](https://adobe.com/go/adobesign_text_tag_guide) 」來增加，以控制「簽署」特定元件Adobe的外觀和位置。 必須在業務流程定義中指定檔來源。 無法在業務程式執行時上傳暫存檔案。

唯一能透過「審核檔步驟」使用Adobe Sign，是能夠將簽署者群組序列化。 簽署者群組可讓您指定依序登入的角色型群組。 Adobe Sign不支援平行簽署群組。

如需設定「審核檔」步驟的協助，請參閱 [ 快速入門手冊 ](https://adobe.com//go/adobesign_workday_quick_start) {target="_blank"} 。

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

Adobe Sign客戶應聯絡其客戶成功經理 （CSM） 尋求支援。 或者，可以透過電話連絡Adobe技術支援：1-866-318-4100;等待產品清單，然後輸入：4 和 2 （依提示操作）。

* [將Adobe文字標籤新增至檔](https://adobe.com/go/adobesign_text_tag_guide)

* [檢閱檔設定和範例](https://www.adobe.com//go/adobesign_workday_quick_start){target="_blank"}

[**連絡Adobe Sign支援人員**](https://www.adobe.com/go/adobesign-support-center)
