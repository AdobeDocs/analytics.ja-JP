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
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Including the Integrate Module{#including-the-integrate-module}

統合コードでは、統合モジュールがAdobe Analyticsのデプロイメント内に存在する必要があります。

導入の一部としてIntegrateモジュールをまだ持っていない場合は、実装のタイプに応じて次の手順を実行してください。

## For AppMeasurement v1.0+ {#section-f28d090bf2404cabaae34cd9c66fc575}

1. **[!UICONTROL Analytics]** / **[!UICONTROL 管理者]** / **[!UICONTROL CodeManagerからダウンロードしたAppMeasurement zipファイルを解凍]**&#x200B;します。

1. Open the file named [!DNL AppMeasurement_Module_Integrate.js].
1. Copy and paste the contents of this file into your primary [!DNL AppMeasurement.js] file.

   >[!NOTE]
   >
   >ファイル内のDO NOT ALTER ANYTHING BELOW THIS LINEコメントの直前に貼り付けます。

## For Legacy Code (H-code) {#section-bba8ad8c715e4f97883e7de3269f681a}

1. Data Connectors UIの「リソース」領域からIntegrateモジュールをダウンロードします（「サポート」タブの下）。

   ![](assets/h_code.png)

1. Copy and paste the contents of that file into your [!DNL s_code] file.

   >[!NOTE]
   >
   >ファイル内のDO NOT ALTER ANYTHING BELOW THIS LINEコメントの直前に貼り付けます。

