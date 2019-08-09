---
description: 統合コードでは、統合モジュールがAdobe Analyticsのデプロイメント内に存在する必要があります。
seo-description: 統合コードでは、統合モジュールがAdobe Analyticsのデプロイメント内に存在する必要があります。
seo-title: Integrateモジュールのインクルード
title: Integrateモジュールのインクルード
uuid: e574f3db-49fa-4f72- bcf- fd98540d3198
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Integrateモジュールのインクルード{#including-the-integrate-module}

統合コードでは、統合モジュールがAdobe Analyticsのデプロイメント内に存在する必要があります。

導入の一部としてIntegrateモジュールをまだ持っていない場合は、実装のタイプに応じて次の手順を実行してください。

## AppMeasurement v1.0以降の場合 {#section-f28d090bf2404cabaae34cd9c66fc575}

1. **[!UICONTROL Analytics]** / **[!UICONTROL 管理者]** / **[!UICONTROL CodeManagerからダウンロードしたAppMeasurement zipファイルを解凍]**&#x200B;します。

1. ファイルを開き [!DNL AppMeasurement_Module_Integrate.js]ます。
1. このファイルのコンテンツをコピーしてプライマリ [!DNL AppMeasurement.js] ファイルに貼り付けます。

   >[!NOTE]
   >
   >ファイル内のDO NOT ALTER ANYTHING BELOW THIS LINEコメントの直前に貼り付けます。

## レガシーコード（Hコード） {#section-bba8ad8c715e4f97883e7de3269f681a}

1. Data Connectors UIの「リソース」領域からIntegrateモジュールをダウンロードします（「サポート」タブの下）。

   ![](assets/h_code.png)

1. ファイルの内容をコピーして、ファイルに [!DNL s_code] 貼り付けます。

   >[!NOTE]
   >
   >ファイル内のDO NOT ALTER ANYTHING BELOW THIS LINEコメントの直前に貼り付けます。

