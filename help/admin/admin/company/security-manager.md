---
description: レポーティングデータに対するアクセスを制御できます。オプションには、強力なパスワード、パスワード有効期限、IP ログイン制限、電子メールドメイン制限などがあります。
title: セキュリティマネージャー
feature: Company Settings
exl-id: 6dcf0354-4b4a-4bd5-ba6c-ae42c7b9e4df
source-git-commit: 5a5a1e48e348f614cb0f0356404903c16c55ceb8
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 100%

---

# セキュリティマネージャー

セキュリティマネージャーを使用すると、レポートデータへのアクセスを管理できます。オプションには、強力なパスワード、パスワード有効期限、IP ログイン制限、電子メールドメイン制限などがあります。

## 設定

**[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL すべての管理者]**／**[!UICONTROL カンパニー設定]**／**[!UICONTROL セキュリティ]**

| 設定 | 説明 |
| --- | --- |
| 堅牢なパスワードを要求 | ユーザーに以下のルールに従ってより安全なパスワードを作成させます。 <ul><li>8 文字以上であること。</li><li>最初と最後の文字の間に 1 文字以上の記号または数字を含むこと。</li><li>1 文字以上の英字を含むこと。</li><li>辞書（英語）に載っている 1 語または複数の単語を含まないこと。</li><li>ログインユーザー名にある連続した 3 文字を含まないこと。</li><li>最近使用した 10 個のパスワードと異なること。</li></ul>**注意**：この機能は、今後新しいパスワードを設定するときに強制的に適用されるものです。既存のパスワードを確認したり、ユーザーに既存のパスワードを変更させたりすることはありません。このため、ユーザーがパスワードを変更して堅牢なパスワード規則に順守するように、パスワードの有効期限を有効にすることを考慮してください。 |
| パスワードの有効期限 | ユーザーにアカウントパスワードを定期的に強制的に変更させます。パスワードが期限切れになる間隔を指定したり、パスワードを即座に無効にしたりできます。 |
| IP ログイン制限の実施 | （この機能は 2021年1月をもって利用できなくなりました）<br>レポート アクセスを特定の IP アドレスまたは IP アドレス範囲に限定します。IP アドレスフィルターリストには、最大 100 個のエントリを追加でき、各エントリには特定のアドレスまたはアドレスの範囲を指定できます。IP ログイン制限の実施は、「IP アドレスフィルター」リストに少なくとも 1 つのエントリが存在する状態になるまで適用されません。許可された IP アドレス：IP アドレス範囲を指定するには、範囲を角括弧で囲みます（例：`192.168.10.[20-240]`）。ワイルドカードを使用して、0 から 255 までの任意の数を指定することもできます（例：`192.168.[10-14].*8`）。失敗したログインはログに記録され、[使用状況およびアクセスログ](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/logs.html?lang=ja#section_6FBAF92D9EA244809C45A78A2F0A7232)に表示されます。 |
| 電子メールドメイン制限の強制 | Analytics がブックマーク、ダウンロード可能なレポートおよびアラートを送信する電子メールアドレスおよびドメインをフィルターします。電子メールフィルターリストでは、最大 100 個のエントリをサポートし、各エントリは電子メールアドレスか電子メールドメイン全体を指定できます。許可されていない電子メールの送信先が予定レポートに含まれる場合、Analytics は、問題の電子メール通知とレポートのスケジュールを解除するためのリンクを送信します&#x200B;**[!UICONTROL 電子メールドメイン制限の強制]**&#x200B;は、許可された電子メールドメインフィルターリストに少なくとも 1 つのエントリが存在するまで適用されません。**[!UICONTROL 許可されたメールアドレスおよびドメイン]**：IP アドレス範囲を指定するには、範囲を角括弧で囲みます（例：`192.168.10.[20-240]`）。ワイルドカードを使用して、0 から 255 までの任意の数を指定することもできます（例：`192.168.[10-14].*`） |
| パスワードリカバリの通知 | ユーザーがユーザーアカウントのパスワードをリセットしようとすると、指定された管理者に通知します。**[!UICONTROL 利用可能な管理者]**：すべての管理者が表示されます。Ctrl キーを押しながらクリックまたは Shift キーを押しながらクリックして複数の管理者を選択できます。**[!UICONTROL 電子メールメンバー]**：現在定義済みの電子メールグループが表示されます。 |