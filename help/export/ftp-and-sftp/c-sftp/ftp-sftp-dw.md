---
description: アドビでは、Data Warehouse リクエストの SFTP サーバーへの書き出しをサポートしています。
keywords: ftp;sftp
title: SFTP サーバーへの Data Warehouse リクエストの送信
feature: FTP Export
exl-id: 45694647-69ec-45e3-b614-4a936909a338
source-git-commit: d8bfad5d388f906c7c7301a9126813f5c2a5dbaa
workflow-type: ht
source-wordcount: '255'
ht-degree: 100%

---

# SFTP サーバーへの Data Warehouse リクエストの送信

アドビでは、[Data Warehouse リクエストのレポートの宛先を設定する](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)の記事の [SFTP](/help/export/data-warehouse/create-request/dw-request-report-destinations.md#sftp) に記載されているように、SFTP サーバーへの Data Warehouse リクエストの書き出しをサポートしています。

以下の作業が完了していることを確認してください。

* Data Warehouse レポートをリクエストする場合、ポート 22 のみを使用する。
* アドビの `authorized_keys` ファイルが、ログインに使用したユーザーのルートディレクトリ内の `.ssh` ディレクトリにある。
* 接続先が `ftp.omniture.com` ではないこと。アドビの内部サーバー間では、SFTP プロトコルはサポートされていません。
* 接続先で、1 要素（PKI）認証がサポートされていること。2 要素のチャレンジがある場合、レポートの配信は失敗します。サーバーが二要素認証を試行するように設定されていないことを確認してください。Adobe Analytics では、ログインに鍵のみを使用し、その他のものは使用しません。
* アドビでは、SSHv2 暗号化をサポートしています。SSHv2 が使用できない場合は、SSHv1 を使用します（RSA 鍵のみ）。

Data Warehouse リクエストを SFTP 経由で正常に送信するには：

1. [Data Warehouse リクエストのレポート先の設定](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)の記事にある、[SFTP](/help/export/data-warehouse/create-request/dw-request-report-destinations.md#sftp) に記載されている手順に従います（公開鍵のダウンロードを含む）。
1. Data Warehouse リクエストに使用されているのと同じ資格情報で、SFTP サイトにログインします。
1. ルートディレクトリの下の `.ssh` という名前のフォルダーに移動し（存在しない場合はこのフォルダーを作成します）、`authorized_keys` ファイルをそこに配置します。

1. Data Warehouse リクエストをまだ完了していない場合は、[Data Warehouse リクエストのレポート先の設定](/help/export/data-warehouse/create-request/dw-request-report-destinations.md).の説明に従って完了します。
