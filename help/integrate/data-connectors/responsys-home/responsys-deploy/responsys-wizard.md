---
description: Data Connectorsインターフェイスで統合ウィザードを完了する手順です。
seo-description: Data Connectorsインターフェイスで統合ウィザードを完了する手順です。
seo-title: Adobe統合ウィザードの完了
solution: Analytics
title: Adobe統合ウィザードの完了
uuid: fb106251-78cf-4a2a-8ba2-2a39188ba910
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Completing the Adobe Integration Wizard{#completing-the-adobe-integration-wizard}

Data Connectorsインターフェイスで統合ウィザードを完了する手順です。

1. Adobe Marketing Cloud内のData Connectors（以前のGenesis）領域に移動します。
1. Responsys統合ウィザードを起動します。
1. 目的のレポートスイートを選択し、統合の名前を指定します。
1. 次の項目を設定します。

   | 項目 | 説明 |
   |---|---|
   | 電子メールアドレス | プライマリ連絡先の電子メールアドレス |
   | 説明 | （オプション）この統合設定の説明 |
   | アカウントID | support@responsys.comサポートチーム（）にお問い合わせください |

1. **[!UICONTROL 次の変数マッピング]** 項目を設定します。

   | 項目 | 説明 |
   |---|---|
   | メッセージID | メッセージIDをリアルタイムで収集するeVarを選択します。 |
   | Recipient ID | 受信者IDをリアルタイムで収集するeVarを選択します。 |
   | 合計バウンス | 数値イベントを選択して、毎日の回答をResponsesysから受信します。 |
   | 電子メール送信済み | 数値イベントを選択して、毎日回答を受信するための数値イベントを選択します。 |
   | クリック済み | 数値イベントを選択して、回答者の毎日のクリック数を受信します。 |
   | 開封済み | 毎日合計を受信する数値イベントを回答者から選択します。 |
   | 登録解除 | 数値イベントを選択して、毎日の応答をResponsesysから受信します。 |
   | 配信済み | 毎日の応答を受信する数値イベントを選択します。 |

1. データアクセスを有効にし、データ収集を設定します。
   1. 必要に応じて分類の名前を変更します。
   1. **[!UICONTROL パートナーセグメント]** は、統合に含まれる標準再マーケティングセグメントです。
   1. **[!UICONTROL 「アクセス要求]**」のチェックボックスをオンにして、毎日再マーケティングセグメントの「回答者」に製品情報をエクスポートできるようにします。
   1. Analytics収集コードを手動で更新するか、自動ソリューションを使用してIDを収集するかを設定します。**[!UICONTROL 「自動ソリューション]**」を選択した場合は、IDを渡すための電子メールリンクで使用するパラメーターを含める必要があります。
1. Review all configuration items and click **[!UICONTROL Activate Now]**.
