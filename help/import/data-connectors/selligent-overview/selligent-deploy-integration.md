---
description: この統合のデプロイは、簡単な 3 ステップのプロセスです。
title: 統合のデプロイ
uuid: c578bf26-34c2-44ea-8e60-2990273f8659
translation-type: tm+mt
source-git-commit: a02fb674ea71a05e085c8e9b2dc4460f62f2cd51
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 100%

---


# 統合のデプロイ {#deploying-the-integration}

この統合のデプロイは、簡単な 3 ステップのプロセスです。

## 統合ウィザードの完了 {#completing-the-integration-wizard}

統合をアクティブ化するには、Data Connectors インターフェイス内で Selligent 統合ウィザードを完了する必要があります。

1. Adobe Experience Cloud 内の Data Connectors 領域に移動します。

   ![](assets/selligent-data_connectors.png)

1. 「**[!UICONTROL 統合を追加]**」で、Selligent プラグインを Adobe Experience Cloud にドラッグ&amp;ドロップします。

   ![](assets/selligent-add_integration.png)

   これにより、Selligent Data Connectors 統合が開きます。

1. **統合設定**：目的のレポートスイートを選択し、「**[!UICONTROL 統合の設定]**」で統合の名前を指定します。

1. 「**[!UICONTROL カスタム値]**」で、Selligent アカウント関連の情報をすべて入力します。

   ![](assets/selligent-general_settings.png)

1. **変数マッピング**：ドロップダウンメニューから適切な予約済み eVar およびイベントを選択します。

   ![](assets/selligent-variables.png)

1. **データ設定**：自動化された 3 つの **[!UICONTROL Partner]** セグメントの他に「**[!UICONTROL セグメント]**」で自分のセグメントを選択することもできます。

1. この統合では、いくつかのデータポイントを Selligent アカウントにダウンロードする必要が出る場合があります。「**[!UICONTROL アクセス要求]**」で同じアクセス権を与えることもできます。
1. 「**[!UICONTROL データ収集]**」で、自動または手動のソリューション（JavaScript プラグイン）を選択し、ランディングページの URL からクエリー文字列パラメーターを収集します。自動化ソリューションを選択する場合は、メッセージ ID（MID）と受信者 ID（RID）のクエリー文字列パラメーターを入力します。JavaScript プラグインについては、アドビコンサルタントにお問い合わせください。
1. **レポート設定**：「**[!UICONTROL ダッシュボードの生成]**」で、チェックボックスをオンにして Selligent ダッシュボードを自動的に生成します。

   ![](assets/selligent-report_settings.png)

1. 統合の概要を確認し、「**[!UICONTROL アクティブ化]**」をクリックします。

## Selligent 内の設定 {#configuration-within-selligent}

Adobe Analytics 内で統合が有効になるとすぐに、Selligent 側で自動設定が有効になります。

すべての電子メールを追跡するトラッカーが作成されました。特定のドメインに制限する場合は、トラッカーの設定を更新してください。

URL 内の Adobe Analytics のトラッキングパラメーターを最前面に移動することを強くお勧めします。これにより、Adobe 処理ルールはランディングページの URL から確実にパラメーターを取得できます。以下に示すチェックボックスをオンにして、トラッキングを有効にします。

![](assets/selligent-tracker.png)

## 統合の確認 {#verifying-the-integration}

すべてのデプロイメント手順が完了したら、統合によってデータが正常に転送されていることを検証できます。

データ交換が始まるまでに数日かかります。統合をアクティブ化した後で、Selligent に連絡するようにしてください。

### 統合アクティビティログ {#section-927e270495db479fba9578915d9ae9c9}

Data Connectors 内で Selligent 統合に移動します。「**[!UICONTROL サポート]**」タブ、「指標データは正常にインポートされました」や「分類データは正常にインポートされました」などのイベントが表示されます。

![](assets/selligent-verifying.png)

### レポートデータ {#section-ebd481a162324e66bd6dc8cb4b8d2424}

適切な指標を使用して Selligent メッセージレポートを表示します。

1. Adobe Experience Cloud の Report &amp; Analytics に移動します。
1. 適切なレポートスイートを選択します。
1. 「**[!UICONTROL カスタムコンバージョン]**」で、「**[!UICONTROL メッセージ ID レポート]**」を選択し、「**[!UICONTROL メッセージ ID / メッセージ名]**」を選択します。
