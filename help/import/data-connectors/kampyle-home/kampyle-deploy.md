---
description: 'null'
title: 統合のデプロイ
uuid: ebb385ca-7bfb-4cd3-9ff6-a5f5a52db5c9
translation-type: tm+mt
source-git-commit: 61df62a6f7089ce7d0308e3b62664176b76e520e

---


# 統合のデプロイ {#deploying-the-integration}

この統合の展開は、Adobe統合ウィザードの完了、プラグインコード(JavaScript)の展開、統合の検証を簡単に行うプロセスです。

## Adobe 統合ウィザードの完了 {#complete-the-adobe-integration-wizard}

統合をアクティブ化するには、Data Connectorsインターフェイスの設定ウィザードを完了します。

1. Adobe Experience Cloud にログインします。
1. に移動しま **[!UICONTROL Data Connectors]**&#x200B;す。
1. Kampyle 統合ウィザードを起動します。
1. 目的のレポートスイートを選択し、統合の名前を指定します。
1. 次のフィールドを設定します。
   1. **[!UICONTROL Email address]**: 主要連絡先の電子メールアドレス.
   1. **[!UICONTROL Description]** （オプション）:この統合設定の説明。
   1. **[!UICONTROL Kampyle Key]**:このキーは、Kampyleアプリケーションの>の下にあ **[!UICONTROL Feedback Form]** ります **[!UICONTROL Feedback Form Customization]**。
   1. **[!UICONTROL Tracking Server]**:Adobe Analyticsデータの追跡に使用するトラッキングサーバーの値。
   1. **[!UICONTROL Tracking Server Secure]**:トラッキングサーバーが安全な/httpsトラフィックと異なる場合は、ここで設定します。
1. Configure the following **[!UICONTROL Variable Mappings]** items:
   1. **[!UICONTROL Kampyle Feedback ID]**:使用可能なeVar変数をレポートスイートから選択します。
   1. **[!UICONTROL Feedback Grade]**:レポートスイートから使用可能な成功イベント（「カウンター」と入力）を選択します。
   1. **[!UICONTROL Feedback Items]**:レポートスイートから使用可能な成功イベント（「カウンター」と入力）を選択します。
   1. **[!UICONTROL Feedback with Grade]**:レポートスイートから使用可能な成功イベント（「カウンター」と入力）を選択します。
1. Kampyle 統合ダッシュボードを自動的に作成する場合は、このチェックボックスをオンにします（推奨）。
1. Review all configuration items and click **[!UICONTROL Activate Now]**.

## 統合設定オブジェクトのデプロイ {#deploy-the-integration-configuration-object}

統合ウィザードの完了後、統合設定オブジェクトをWebプロパティにデプロイします。 多くの場合、統合設定オブジェクトをデプロイする最も簡単な方法は、それらのオブジェクトを Adobe Analytics デプロイメントコードに含めることです。

> [!NOTE] Adobe Experience Platform Launchを使用する場合は、このツールを使用して統合設定オブジェクトを簡単に追加できます。

1. Navigate to the **[!UICONTROL Resources]** > **[!UICONTROL Support]** tab of the integration.
1. リソースをダウンロードして保 **[!UICONTROL Kampyle Integration Code (JS)]** 存します。 コードは次のようになります。

   ```
   /* Kampyle:  Integration configuration settings */
     window.k_sc_param = { "version":1.1 }
   ```

1. 次のいずれかの方法を使用してコードをデプロイします。

   * Adobe Experience Platform Launchを使用します。
   * Adobe Analyticsの導入を維持する組織のリソースにコードを配信します。

## 統合の検証 {#verify-the-integration}

いくつかのチェックを完了して、統合がデータを正常に転送したことを検証します。

### 統合アクティビティログ {#section-0472df9180db4f218db5f6040cab07af}

View your Kampyle integration setup within the Adobe Experience Cloud by navigating to **[!UICONTROL Support]** > **[!UICONTROL Integration Activity Log]**. Under the **[!UICONTROL Data In]** tab, you should see entries stating that classification data was successfully imported.

> [!NOTE] ログエントリは、通常、展開が成功した24時間以内に表示されます。

![統合アクティビティログ](assets/integration_activity_log.png)

### アドビのレポートデータ {#section-1ae9f0a5e6bc40988478ff55aefd56ac}

Kampyle フィードバックレポートを Adobe Analytics で表示するには、適切なメニュー構造内で Kampyle レポートに移動します。

> [!NOTE]統合フィードバックフォームが積極的に送信を受け取っていると想定して、レポートデータは、デプロイメントが成功してから 24 ～ 48 時間以内に表示されます。

![アドビのレポートデータ](assets/adobe_reporting_data.png)
