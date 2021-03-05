---
description: Adobe Analyticsで使用するResponsysデータコネクタをデプロイします。
title: 統合のデプロイ
uuid: 5abf6d49-b05b-4e0f-8d9b-bb02d8f1c84a
translation-type: tm+mt
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 96%

---


# 統合のデプロイ {#deploying-the-integration}

この統合のデプロイは、以下の操作を必要とする簡単なプロセスです。

## アドビ統合ウィザードの完了 {#completing-the-adobe-integration-wizard}

Data Connectors インターフェイスで統合ウィザードを完了する手順です。

1. Adobe Experience Cloud 内の Data Connectors（旧称 Genesis）領域に移動します。
1. Responsys 統合ウィザードを起動します。
1. 目的のレポートスイートを選択し、統合の名前を指定します。
1. 次のフィールドを設定します。

   | 項目 | 説明 |
   |---|---|
   | 電子メール住所 | 主要連絡先の電子メールアドレス |
   | 説明 | （オプション）この統合設定の説明 |
   | アカウント ID | support@responsys.com から Responsys サポートチームに連絡して入手します |

1. 次の「**[!UICONTROL 変数マッピング]**」項目を設定します。

   | 項目 | 説明 |
   |---|---|
   | メッセージ ID | リアルタイムでメッセージ ID を収集する eVar を選択します。 |
   | 受信者 ID | リアルタイムで受信者 ID を収集する eVar を選択します。 |
   | バウンス数合計 | Responsys からの日別のバウンスを受け取る数値イベントを選択します。 |
   | 送信済み電子メール | Responsys からの日別の送信数を受け取る数値イベントを選択します。 |
   | クリック済み | Responsys からの日別の合計クリック数を受け取る数値イベントを選択します。 |
   | 開封済み | Responsys からの日別の合計開封数を受け取る数値イベントを選択します。 |
   | 登録解除 | Responsys からの日別の登録解除数を受け取る数値イベントを選択します。 |
   | 配信済み | Responsys からの日別の配信数を受け取る数値イベントを選択します。 |

1. データアクセスを有効にし、データ収集を設定します。
   1. 必要に応じて分類の名前を変更します。
   1. **[!UICONTROL Partner セグメント]**&#x200B;は、統合に含まれる標準のリマーケティングセグメントです。
   1. 「**[!UICONTROL アクセス要求]**」から、日別のリマーケティングセグメントで製品情報を Responsys に書き出しできるようにするチェックボックスをオンにします。
   1. ID を収集するかどうかは、Analytics コレクションコードを手動で更新するか、自動ソリューションを使用して設定します。「**[!UICONTROL 自動ソリューション]**」を選択した場合は、電子メールリンクで ID を渡すために使用するパラメーターを含める必要があります。
1. すべての設定項目を確認し、「**[!UICONTROL 今すぐアクティブ化]**」をクリックします。

## Responsys システム内での設定 {#configuring-within-the-responsys-system}

統合をアクティブ化するには、Responsys サポートへの連絡が必要になります。

統合ウィザードを完了したら、Responsys 内で統合をアクティブ化する必要があります。

その場合は、support@responsys.com で Responsys サポートチームにお問い合わせください。
