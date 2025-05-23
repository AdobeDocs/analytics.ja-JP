---
title: Adobe AnalyticsでReport Builderを設定する方法
description: オフラインモード、言語、基準日、トラブルシューティングの設定方法について説明します。
role: Admin
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: d158ad45-d467-4355-b091-f015bde7a243
source-git-commit: ec14dde5b0e91a9fcfb217a811d36af2eea5f772
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 83%

---

# Report Builder の設定

「**設定**」ペインを使用して、UI で表示される言語やオフラインモードで動作するかどうかなど、アプリケーションレベルの設定を行います。設定は直ちに適用され、変更されるまで、今後のすべてのセッションに対して設定されます。

Report Builder 設定を変更するには

1. 「**設定**」アイコンをクリックします。

1. 「オフラインモードの有効化」、「言語の選択」、「トラブルシューティングのログ設定の有効化」などの変更を行います。

1. 「**適用**」をクリックします。

   ![Report Builderの設定。](./assets/image38.png)

## オフラインモード

オフラインモードでデータブロックを作成および編集する場合、データは取得されません。代わりに、リクエストの実行を待たずに、データブロックをすばやく作成および編集できるよう、シミュレーションデータを使用します。オンラインに戻ったときに、「*データブロックの更新*」コマンドまたは「*すべてのデータブロックの更新*」コマンドを使用すると、作成したデータブロックが実際のデータに更新されます。

オフラインモードを有効にするには

1. 「**[!UICONTROL 設定]**」アイコンをクリックします。

1. **[!UICONTROL Enable off-line mod]e** を選択します。

1. 「**[!UICONTROL ダミーデータの表示方法]**」フィールドに正の整数を入力します。

1. 「**[!UICONTROL 適用]**」をクリックします。

## 言語

Report Builder UI の言語を選択できます。サポートされている Adobe Analytics の言語はすべて利用できます。

Report Builder UI で使用する言語を選択するには

1. 「設定」をクリックします。

1. 「**[!UICONTROL 言語]**」ドロップダウンメニューから言語を選択します。

   ![ 英語が選択されたReport Builderの一覧を表示する言語の日付範囲ウィンドウ。](./assets/image39.png)

1. 「**[!UICONTROL 適用 &#x200B;]」をクリック** ます。

## トラブルシューティング

トラブルシューティング設定を使用して、すべてのクライアント／サーバーデータをローカルファイルに記録します。このオプションを使用して、サポートチケットの解決に役立てます。

「トラブルシューティング」オプションを有効にするには、「**[!UICONTROL Report Builder データブロックを web コンソールに記録]**」を選択します。
