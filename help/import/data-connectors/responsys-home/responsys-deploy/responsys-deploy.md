---
description: 'null'
seo-description: 'null'
seo-title: 統合のデプロイ
solution: Analytics
title: 統合のデプロイ
uuid: 5abf6d49-b05b-4e0f-8d9b-bb02d8f1c84a
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# 統合のデプロイ{#deploying-the-integration}

この統合の展開は、以下の操作を必要とする簡単なプロセスです。

## Adobe統合ウィザードの完了{#completing-the-adobe-integration-wizard}

Data Connectorsインターフェイスで統合ウィザードを完了する手順です。

1. Adobe Experience cloud内のData Connectors（旧称Genesis）領域に移動します。
1. Responsys統合ウィザードを起動します。
1. 目的のレポートスイートを選択し、統合の名前を指定します。
1. 次の項目を設定します。

   | 項目 | 説明 |
   |---|---|
   | 電子メールアドレス | 主連絡先の電子メールアドレス |
   | 説明 | （オプション）この統合設定の説明 |
   | アカウントID | support@responsys.comからResponsysサポートチームに連絡して入手 |

1. 次の「 **[!UICONTROL Variable Mappings]** 」項目を設定します。

   | 項目 | 説明 |
   |---|---|
   | メッセージID | メッセージIDをリアルタイムで収集するeVarを選択します。 |
   | Recipient ID | 受信者IDをリアルタイムで収集するeVarを選択します。 |
   | 合計バウンス数 | Responsysから日別のバウンスを受け取る数値イベントを選択します。 |
   | 電子メール送信 | Responsysから毎日の送信を受信する数値イベントを選択します。 |
   | クリック済み | Responsysから日別合計クリック数を受け取る数値イベントを選択します。 |
   | 開封済み | Responsysから日別合計開封数を受け取る数値イベントを選択します。 |
   | 登録解除 | Responsysから毎日購読解除を受け取る数値イベントを選択します。 |
   | 配信済み | Responsysから日別配信を受け取る数値イベントを選択します。 |

1. データアクセスを有効にし、データ収集を設定します。
   1. 必要に応じて分類の名前を変更します。
   1. **[!UICONTROL パートナーセグメント]** は、統合に含まれる標準のリマーケティングセグメントです。
   1. 「アクセ **[!UICONTROL スリクエスト]**」で、製品情報をResponsysに毎日のリマーケティングセグメントでエクスポートできるようにするチェックボックスをオンにします。
   1. IDを収集するかどうかは、Analyticsコレクションコードを手動で更新するか、自動化ソリューションを使用して設定します。 「 **[!UICONTROL Automated Solution」を選択する場合]**、IDを渡すための電子メールリンクで使用するパラメーターを含める必要があります。
1. すべての設定項目を確認し、「今すぐアクティブ化」 **[!UICONTROL をクリックしま]**&#x200B;す。

## 応答システム内での設定{#configuring-within-the-responsys-system}

統合のアクティブ化には、Responsysサポートに問い合わせる必要があります。

統合ウィザードを完了したら、Responsys内で統合をアクティブ化する必要があります。

その場合は、support@responsys.comでResponsysサポートチームにお問い合わせください。