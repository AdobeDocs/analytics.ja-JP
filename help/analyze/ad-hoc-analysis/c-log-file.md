---
title: ログファイル
description: トラブルシューティング用にログファイルを取得します。
translation-type: tm+mt
source-git-commit: d4cb2acb4ecaecce3644a2f3cf29913440e5cd6a
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 5%

---


# ログファイル

>[!IMPORTANT]
>
>Adobeは、2021年3月1日にAd Hoc Analysisを廃業に移す予定です。 [詳細情報...](https://adobe.ly/discoverworkspace).

Ad Hoc Analysisの問題のトラブルシューティングを行う場合、ログファイルの取得が必要になる場合があります。 Adobeは、ログファイルを使用して問題の根本原因を特定し、解決を提供できます。 この `discover.log` ファイルには、すべてのセッションにわたるすべてのユーザーインタラクション、レポートの読み込み情報およびJavaエラーメッセージが含まれます。 ユーザーのパスワードなど、保護されている情報をハッシュします。 大きいログファイルは、10 MB単位に分割されます。 ログファイルをAdobeに提供する場合は、すべてのファイルが選択されていることを確認します。

## Windows

Windows用の `discover.log` ファイルの取得：

1. [開始]メニューをクリックして[ **実行**]を選択するか、 [ `[Win]` +]を押し `[R]`ます。
2. 次をテキストフィールドに貼り付け、「 **OK**」をクリックします。

   ```text
   %appdata%/../Local/Adobe/Discover/log
   ```

3. フォルダー内のすべてのファイルをハイライト表示し、右クリックして、 **送信先/圧縮（zip形式）フォルダーを選択します**。
4. Adobeの担当者に.zipファイルを伝えます。

## Mac

Mac OS用の `discover.log` ファイルを取得するには、次の手順を実行します。

1. ファインダーを開き、 `/Users/your-user/.adobe/Discover/log`
2. フォルダ内のすべてのファイルをハイライト表示し、右クリックして「 **圧縮**」を選択します。
3. Adobeの担当者に.zipファイルを伝えます。

圧縮ファイルの合計サイズが10 MBを超える場合は、Adobeの担当者が一時的なFTPの場所を指定できます。
