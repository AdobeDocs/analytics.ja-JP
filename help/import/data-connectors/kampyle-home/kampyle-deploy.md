---
description: Adobe AnalyticsにKampyleデータコネクタをデプロイします。
title: 統合のデプロイ
uuid: ebb385ca-7bfb-4cd3-9ff6-a5f5a52db5c9
exl-id: ac8e1f30-cefe-448a-bec6-cda58ee51025
source-git-commit: 9a70d79a83d8274e17407229bab0273abbe80649
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 46%

---

# 統合のデプロイ{#deploying-the-integration}

この統合のデプロイは、Adobe統合ウィザードの完了、プラグインコード(JavaScript)のデプロイ、統合の検証から成る簡単なプロセスです。

## Adobe 統合ウィザードの完了 {#complete-the-adobe-integration-wizard}

統合をアクティブ化するには、Data Connectorsインターフェイスで設定ウィザードを完了します。

1. [!DNL Adobe Experience Cloud]にログインします。
1. **[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL すべての管理者]** ／**[!UICONTROL Data Connectors]** をクリックします。
1. Kampyle 統合ウィザードを起動します。
1. 目的のレポートスイートを選択し、統合の名前を指定します。
1. 次のフィールドを設定します。
   1. **[!UICONTROL 電子メールアドレス]**:主要連絡先の電子メールアドレス。
   1. **[!UICONTROL 説明]** （オプション）:この統合設定の説明。
   1. **[!UICONTROL Kampyleキー]**:このキーは、Kampyleアプリケーションの **[!UICONTROL フィードバックフォーム]** / **[!UICONTROL フィードバックフォームのカスタマイズ]**&#x200B;の下で確認できます。
   1. **[!UICONTROL トラッキングサーバー]**:Adobe Analyticsデータの追跡に使用するトラッキングサーバー値。
   1. **[!UICONTROL トラッキングサーバー保護]**:セキュリティで保護されたトラフィックやhttpsトラフィックのトラッキングサーバーが異なる場合は、ここでその設定を指定します。
1. 次の「**[!UICONTROL 変数マッピング]**」項目を設定します。
   1. **[!UICONTROL KampyleフィードバックID]**:使用可能なeVar変数をレポートスイートから選択します
   1. **[!UICONTROL フィードバックグレード]**:レポートスイートから利用可能な成功イベント（タイプ「カウンター」）を選択します。
   1. **[!UICONTROL フィードバック項目]**:レポートスイートから利用可能な成功イベント（タイプ「カウンター」）を選択します。
   1. **[!UICONTROL グレード付きフィードバック]**:レポートスイートから利用可能な成功イベント（タイプ「カウンター」）を選択します。
1. Kampyle 統合ダッシュボードを自動的に作成する場合は、このチェックボックスをオンにします（推奨）。
1. すべての設定項目を確認し、「**[!UICONTROL 今すぐアクティブ化]**」をクリックします。

## 統合設定オブジェクトのデプロイ {#deploy-the-integration-configuration-object}

統合ウィザードを完了したら、統合設定オブジェクトをWebプロパティにデプロイします。 多くの場合、統合設定オブジェクトをデプロイする最も簡単な方法は、それらのオブジェクトを Adobe Analytics デプロイメントコードに含めることです。

>[!NOTE]
>
>Adobe Experience Platformでタグを使用する場合、このツールを使用して統合設定オブジェクトを簡単に追加できます。

1. 統合の&#x200B;**[!UICONTROL リソース]**／**[!UICONTROL サポート]**&#x200B;タブに移動します。
2. **[!UICONTROL Kampyle 統合コード（JS）リソース]**&#x200B;をダウンロードして保存します。コードは次のようになります。

   ```
   /* Kampyle:  Integration configuration settings */
     window.k_sc_param = { "version":1.1 }
   ```

3. 次のいずれかの方法を使用してコードをデプロイします。

   * Adobe Experience Platformでタグを使用します。
   * Adobe Analyticsのデプロイメントを維持する組織のリソースにコードを配信します。

## 統合の検証 {#verify-the-integration}

いくつかの確認を完了して、統合によってデータが正常に転送されたことを検証します。

### 統合アクティビティログ {#section-0472df9180db4f218db5f6040cab07af}

**[!UICONTROL サポート]**／**[!UICONTROL 統合アクティビティログ]**&#x200B;に移動して、Adobe Experience Cloud 内で Kampyle 統合の設定を表示します。「**[!UICONTROL データの場所]**」タブに、分類データが正常に読み込まれたことを示すエントリが表示されます。

>[!NOTE]
>
>ログエントリは、通常、デプロイメントが成功してから24時間以内に表示されます。

![統合アクティビティログ](assets/integration_activity_log.png)

### アドビのレポートデータ {#section-1ae9f0a5e6bc40988478ff55aefd56ac}

Kampyle フィードバックレポートを Adobe Analytics で表示するには、適切なメニュー構造内で Kampyle レポートに移動します。

>[!NOTE]
>
>統合フィードバックフォームが積極的に送信を受け取っていると想定して、レポートデータは、デプロイメントが成功してから 24 ～ 48 時間以内に表示されます。

![Adobeレポートデータ](assets/adobe_reporting_data.png)
