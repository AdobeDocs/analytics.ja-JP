---
title: データフィードのトラブルシューティング
description: データフィードの問題を特定し解決する方法について説明します。
keywords: ジョブ；トラブルシューティング；エラー；ftp;chdir；接続；ログイン；put
exl-id: c082bc95-cdae-448b-86b5-695660fb2352
source-git-commit: b81ffba2f1e021888dd1c4b016c9b451448f47bb
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 29%

---

# データフィードのトラブルシューティング

ジョブの処理または配信に失敗する可能性がある潜在的な理由を特定します。

## 既存のデータフィードのトラブルシューティング

時間別または日別に正常に動作するが、最近失敗したデータフィードがある場合は、次の各項目を確認してください。

* 以下を使用： [Adobeステータスツール](https://status.adobe.com/en/experience_cloud) をクリックして、定期メンテナンス期間や可用性に関する問題が発生しているかどうかを確認します。 その時点で既知の問題が発生した場合、Adobeは、サービスが復元されると、スケジュールされたデータフィードを自動的に処理します。
* FTP サイトに十分な空き容量があることを確認します。 FTP サイトのディスク容量が不足した場合は、新しいファイルの領域を確保するために、サーバーからいくつかのファイルを削除します。
* 既知の問題がなく、FTP サイトに十分なディスク容量がある場合は、データフィードを再送信できます。

   1. Adobe Analyticsにログインし、に移動します。 **[!UICONTROL 管理者]** > **[!UICONTROL データフィード]**.
   2. 目的のデータフィードを見つけ、再実行する各フィードの横にあるチェックボックスをクリックします。
   3. クリック **[!UICONTROL 再実行]**.

   ![再実行](assets/rerun.png)

再実行後にデータフィードファイルがまだ受け取れない場合は、カスタマーケアにお問い合わせください。

## 新しいデータフィードのトラブルシューティング

新しいデータフィードでエラーが発生した場合は、FTP サイトにテストファイルを手動でアップロードして、問題のトラブルシューティングをおこないます。 ほとんどの場合、これらの手順を使用することで障害の発生地点を判断できます。

1. エクスプローラー（Windows）または Finder（Mac）を使用して FTP サイトにログインします。FTP プロトコル (`ftp://`) と、 [Adobeの IP アドレス](/help/technotes/ip-addresses.md) 組織のファイアウォールを通じて。 FTP サイトにアクセスできない場合は、FTP サイトの所有者と協力して、正しい宛先を判断します。

   ![エクスプローラー](assets/file_explorer.png)

2. ユーザー名とパスワードの入力を求めるポップアップが表示されます。認証資格情報を入力します。資格情報が承認されると、ウィンドウに FTP サイトの現在のコンテンツが表示されます。資格情報が承認されない場合は、FTP の所有者に問い合わせて、ユーザー名とパスワードが正しいことを確認します。 SFTP を使用する場合は、 [SFTP ガイド](../ftp-and-sftp/c-sftp/ftp-sftp.md). なお、Adobeは、一部の SFTP 使用例をサポートしているわけではありません。
3. ファイルを認証ウィンドウにドラッグして、FTP サイトにアップロードします。どの画像やテキストドキュメントでもかまいません。FTP サイトにファイルを配置しようとしてエラーが発生した場合は、FTP の所有者に問い合わせて、十分なディスク容量があり、ユーザー名に FTP サイトへの書き込み権限があることを確認します。
4. ファイルが FTP サイト上に存在することを確認したら、以前の手順でアップロードしたファイルを削除できます。

上記の手順がすべて正常に動作し、それでも FTP エラーが発生する場合は、カスタマーケアにお問い合わせください。