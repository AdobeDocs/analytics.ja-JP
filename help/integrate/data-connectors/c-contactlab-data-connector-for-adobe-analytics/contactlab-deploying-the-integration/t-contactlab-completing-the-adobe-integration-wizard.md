---
description: Data Connectorsインターフェイスで統合ウィザードを完了する手順です。
seo-description: Data Connectorsインターフェイスで統合ウィザードを完了する手順です。
seo-title: Adobe統合ウィザードの完了
solution: Analytics
title: Adobe統合ウィザードの完了
uuid: a8135be3- fba3-436d-8959- faed40b15088
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Completing the Adobe Integration Wizard{#completing-the-adobe-integration-wizard}

Data Connectorsインターフェイスで統合ウィザードを完了する手順です。

1. Adobe Marketing Cloud内のData Connectors（以前のGenesis）領域に移動します。
1. ContactLab統合ウィザードを起動します。
1. 目的のレポートスイートを選択し、統合の名前を指定します。
1. 次の項目を設定します。

   | 項目 | 説明 |
   |---|---|
   | 電子メールアドレス | プライマリ連絡先の電子メールアドレス |
   | 説明 | （オプション）この統合設定の説明 |

1. **[!UICONTROL 次の変数マッピング]** 項目を設定します。

   | 項目 | 説明 |
   |---|---|
   | リンク ID | リンクIDをリアルタイムで収集するeVarを選択します。 |
   | メッセージID | メッセージIDをリアルタイムで収集するeVarを選択します。 |
   | Recipient ID | 受信者IDをリアルタイムで収集するeVarを選択します。 |
   | バウンス | 数値イベントを選択して、ContactLabから日別バウンスを受信します。 |
   | 送信済み | 数値イベントを選択して、ContactLabから日次送信を受信します。 |
   | クリック済み | 数値イベントを選択して、ContactLabからの日別の総クリック数を受信します。 |
   | 開封済み | 数値イベントを選択して、ContactLabから毎日合計を受信します。 |
   | 登録解除 | 数値イベントを選択して、ContactLabから毎日登録解除します。 |

1. データアクセスを有効にし、データ収集を設定します。
   1. 必要に応じて分類の名前を変更します。
   1. **[!UICONTROL パートナーセグメント]** は、統合に含まれる標準再マーケティングセグメントです。
   1. Under **[!UICONTROL Your Segments]**, select any custom segments that you would like to include in this integration. 管理パネルの下に追加のカスタムセグメントを作成できます。
   1. **[!UICONTROL 「アクセス要求]**」のチェックボックスをオンにして、毎日再マーケティングセグメントの製品情報をContactLabにエクスポートできるようにします。
   1. 必要に応じて、計算指標の名前を変更します。
   1. Analytics収集コードを手動で更新するか、自動ソリューションを使用してIDを収集するかを設定します。**[!UICONTROL 「自動ソリューション]**」を選択した場合は、IDを渡すための電子メールリンクで使用するパラメーターを含める必要があります。
1. Review all configuration items and click **[!UICONTROL Activate Now]**.
