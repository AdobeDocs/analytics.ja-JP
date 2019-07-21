---
description: Dynamic Tag Management を Adobe Analytics に手動で導入する場合に AppMeasurement コードを挿入します。
keywords: Dynamic Tag Management;リンクアカウント;アカウントのリンク;コードの編集;appMeasurement;AppMeasurementコード
seo-description: Dynamic Tag Management を Adobe Analytics に手動で導入する場合に AppMeasurement コードを挿入します。
seo-title: コアの AppMeasurement コードの挿入
solution: Marketing Cloud、Analytics、Target、Dynamic Tag Management
title: コアの AppMeasurement コードの挿入
uuid: 3f83fbb1-3ed5-4e45-888a-0a183aac1a90
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# コアの AppMeasurement コードの挿入

Dynamic Tag Management を Adobe Analytics に手動で導入する場合に AppMeasurement コードを挿入します。

1. [!DNL Adobe Analytics] ツールページで **[!UICONTROL 、「一般]** 」セクションを展開し、「エディターを開く」をクリック ****&#x200B;します。
1. Unzip the [!DNL AppMeasurement_JavaScript*.zip] file you downloaded in [deploy Adobe Analytics](../../../implement/c-implement-with-dtm/t-analytics-deploy.md#task_3A00639CADF14C9C844F962222077E4E).

   カスタムライブラリを使用する場合は、このウィンドウを開くと、最新バージョンのコードがあらかじめ取得されています。Admin Console で ZIP ファイルをダウンロードする必要はありません。
1. Open [!DNL AppMeasurement.js] in a text editor.
1. Copy and paste the contents into the **[!UICONTROL Edit Code]** window.

   ![](assets/edit-code.png)

1. Adobe recommends adding the following code above the *`Do Not Alter Anything Below This Line`*:

   ```
   var s_account="INSERT-RSID-HERE"
   var s=s_gi(s_account)
   ```

   >[!IMPORTANT]
   >
   >If you add this code, it is recommended that you also select the **[!UICONTROL Set report suites using custom code below]** checkbox in the overall library settings.

1. **[!UICONTROL 「保存して閉じる]**」をクリックします。

   メディアモジュール、Integrate Module、または実装プラグインを使用している場合、それらをコードセクションに含めることもできます。Dynamic Tag Management のマネージコードは、通常の実装の JavaScript ファイルと同じように記述できます。

