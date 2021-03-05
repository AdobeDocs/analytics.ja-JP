---
description: Adobe Analyticsで使用するContactLab統合を導入します。
title: 統合のデプロイ
uuid: df3f24c9-d2e3-489e-b97e-e1af0d5dd1fa
translation-type: tm+mt
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 97%

---


# 統合のデプロイ {#deploying-the-integration}

この統合のデプロイは、以下の操作を必要とする簡単なプロセスです。

## Adobe 統合ウィザードの完了 {#completing-the-adobe-integration-wizard}

Data Connectors インターフェイスで統合ウィザードを完了する手順です。

1. Adobe Experience Cloud 内の Data Connectors（旧称 Genesis）領域に移動します。
1. ContactLab 統合ウィザードを起動します。
1. 目的のレポートスイートを選択し、統合の名前を指定します。
1. 次のフィールドを設定します。

   | 項目 | 説明 |
   |---|---|
   | 電子メール住所 | 主要連絡先の電子メールアドレス |
   | 説明 | （オプション）この統合設定の説明 |

1. 次の「**[!UICONTROL 変数マッピング]**」項目を設定します。

   | 項目 | 説明 |
   |---|---|
   | リンク ID | リアルタイムでリンク ID を収集する eVar を選択します。 |
   | メッセージ ID | リアルタイムでメッセージ ID を収集する eVar を選択します。 |
   | 受信者 ID | リアルタイムで受信者 ID を収集する eVar を選択します。 |
   | バウンス | ContactLab からの日別のバウンスを受け取る数値イベントを選択します。 |
   | 送信済み | ContactLab からの日別の送信数を受け取る数値イベントを選択します。 |
   | クリック済み | ContactLab からの日別の合計クリック数を受け取る数値イベントを選択します。 |
   | 開封済み | ContactLab からの日別の合計開封数を受け取る数値イベントを選択します。 |
   | 登録解除 | ContactLab からの日別の登録解除数を受け取る数値イベントを選択します。 |

1. データアクセスを有効にし、データ収集を設定します。
   1. 必要に応じて分類の名前を変更します。
   1. **[!UICONTROL Partner セグメント]**&#x200B;は、統合に含まれる標準のリマーケティングセグメントです。
   1. 「**[!UICONTROL セグメント]**」で、この統合に含めるカスタムセグメントを選択します。管理パネルで、追加のカスタムセグメントを作成できます。
   1. 「**[!UICONTROL アクセス要求]**」で、製品情報を、毎日のリマーケティングセグメントの ContactLab に書き出すことを許可するチェックボックスをオンにします。
   1. 必要に応じて計算指標の名前を変更します。
   1. ID を収集するかどうかは、Analytics コレクションコードを手動で更新するか、自動ソリューションを使用して設定します。「**[!UICONTROL 自動ソリューション]**」を選択した場合は、電子メールリンクで ID を渡すために使用するパラメーターを含める必要があります。
1. すべての設定項目を確認し、「**[!UICONTROL 今すぐアクティブ化]**」をクリックします。

## 統合の検証 {#verifying-the-integration}

Adobe Experience Cloud 内で ContactLab 統合設定を表示します。

1. 統合アクティビティログを表示します。
   1. Adobe Experience Cloud で、**[!UICONTROL サポート]**／**[!UICONTROL 統合アクティビティログ]**&#x200B;に移動します。

      ![](assets/integration_activity_log.png)

   1. 「**[!UICONTROL 分類データは正常にインポートされました]**」、「**[!UICONTROL 指標データは正常にインポートされました]**」、「**[!UICONTROL 指標データは正常にエクスポートされました]**」などのエントリを探します。これらのエントリは、デプロイメントが成功してから 1 日以内に表示されます。
1. Adobe Analytics 内でレポートデータを表示します。
   1. **[!UICONTROL カスタムコンバージョン]**／**[!UICONTROL カスタムコンバージョン 1 ～ 10]**／**[!UICONTROL メッセージ ID レポート]**&#x200B;に移動します。

      ![](assets/reporting.png)

   1. ContactLab レポートを探します。このデータは、デプロイメントが成功してから 24 ～ 48 時間以内に表示されます。
