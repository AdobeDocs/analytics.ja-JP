---
description: Dynamic Tag Management を Adobe Analytics に手動で導入する場合に AppMeasurement コードを挿入します。
keywords: Dynamic Tag Management；リンクされたアカウント；アカウントのリンク；コードの編集；appmeasurement;appmeasurementコード
seo-description: Dynamic Tag Management を Adobe Analytics に手動で導入する場合に AppMeasurement コードを挿入します。
seo-title: コアの AppMeasurement コードの挿入
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: コアの AppMeasurement コードの挿入
uuid: 3f83fbb1-3ed5-4e45-888a-0a183aac1a90
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# コアの AppMeasurement コードの挿入

Dynamic Tag Management を Adobe Analytics に手動で導入する場合に AppMeasurement コードを挿入します。

1. On the [!DNL Adobe Analytics] tool page, expand the **[!UICONTROL General]** section, then click **[!UICONTROL Open Editor]**.
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

1. Click **[!UICONTROL Save and Close]**.

   メディアモジュール、Integrate Module、または実装プラグインを使用している場合、それらをコードセクションに含めることもできます。Dynamic Tag Management のマネージコードは、通常の実装の JavaScript ファイルと同じように記述できます。

