---
description: 'null'
title: 統合のデプロイ
uuid: 1a0770a7-c61b-4eec-a9b3-983def842ad8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 100%

---


# 統合のデプロイ {#deploying-the-integration}

この統合のデプロイは、アドビの統合ウィザードの完了と統合の検証から成る簡単なプロセスです。

## アドビ統合ウィザードの完了 {#completing-the-adobe-integration-wizard}

Data Connectors インターフェイスで統合ウィザードを完了する手順です。

1. Adobe Experience Cloud 内の Data Connectors（旧称 Genesis）領域に移動します。
1. Dynamic Signal 統合ウィザードを起動します。
1. 目的のレポートスイートを選択し、統合の名前を指定します。
1. 次のフィールドを設定します。

   | 項目 | 説明 |
   |---|---|
   | 電子メール住所 | 主要連絡先の電子メールアドレス。 |
   | 説明 | （オプション）この統合設定の説明。 |
   | コミュニティ ID | この ID は、Dynamic Signal の担当者から取得できます。 |

1. 次の「**[!UICONTROL 変数マッピング]**」項目を設定します。

   | 項目 | 説明 |
   |---|---|
   | トラッキングコード | レポートスイートから使用可能な eVar 変数を選択します。 |

1. この統合用に作成される分類を確認します。
1. Dynamic Signal 統合ダッシュボードを作成する場合は、このチェックボックスをオンにします（オプションですが、強く推奨します）。
1. すべての設定項目を確認し、「**[!UICONTROL 今すぐアクティブ化]**」をクリックします。
1. **重要**：ウィザードを完了したら、Dynamic Signal の担当者に通知し、VoiceStorm プラットフォームで統合をアクティブ化できるようにする必要があります。

## 統合の確認 {#verifying-the-integration}

Adobe Experience Cloud 内で Dynamic Signal VoiceStorm 統合の設定を表示する手順

1. 統合アクティビティログで Dynamic Signal 統合の設定を確認します。
   1. Adobe Experience Cloud で、**[!UICONTROL サポート]**／**[!UICONTROL 統合アクティビティログ]**&#x200B;に移動します。

      ![](assets/integration_activity_log.png)

   1. 「**[!UICONTROL 分類データは正常にインポートされました]**」などのエントリを探します。これらのエントリは、デプロイメントが成功してから 24 時間以内に表示されます。
1. アドビ統合ウィザード（手順 7）で自動的に作成されたダッシュボードを使用して、Adobe Analytics 内で Dynamic Signal レポートを確認します。また、Adobe Analytics メニュー構造から Dynamic Signal レポートに移動することもできます。次のスクリーンショットを参照してください。

   **注意**：このデータは、デプロイメントが成功してから 24 ～ 48 時間以内に表示されます。

   ![](assets/reporting.png)

   ![](assets/reporting2.png)
