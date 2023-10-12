---
description: アドビでは、Data Warehouse リクエストの SFTP サーバーへの書き出しをサポートしています。
keywords: ftp;sftp
title: SFTP サーバーへの Data Warehouse リクエストの送信
feature: FTP Export
exl-id: 45694647-69ec-45e3-b614-4a936909a338
source-git-commit: d8bfad5d388f906c7c7301a9126813f5c2a5dbaa
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 53%

---

# SFTP サーバーへの Data Warehouse リクエストの送信

Adobeは、SFTP サーバーへのData Warehouseリクエストの書き出しをサポートします ( [SFTP](/help/export/data-warehouse/create-request/dw-request-report-destinations.md#sftp) この記事では [レポートの送信先の設定リクエストのData Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md).

以下の作業をおこないます。

* ポートレポートをリクエストする際には、Data Warehouse22 のみが使用されます。
* Adobe `authorized_keys` ファイルが `.ssh` ディレクトリ内の、ログインするユーザーのルートディレクトリ内にある。
* 接続先が `ftp.omniture.com` ではないこと。アドビの内部サーバー間では、SFTP プロトコルはサポートされていません。
* 接続先で、1 要素（PKI）認証がサポートされていること。2 要素のチャレンジがある場合、レポートの配信は失敗します。サーバーが二要素認証を試行するように設定されていないことを確認してください。Adobe Analytics では、ログインに鍵のみを使用し、その他のものは使用しません。
* アドビでは、SSHv2 暗号化をサポートしています。SSHv2 が使用できない場合は、SSHv1 を使用します（RSA 鍵のみ）。

Data Warehouse リクエストを SFTP 経由で正常に送信するには：

1. 次に示す手順を実行します： [SFTP](/help/export/data-warehouse/create-request/dw-request-report-destinations.md#sftp) この記事では [レポートの送信先の設定リクエストのData Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)（公開鍵のダウンロードを含む）
1. Data Warehouseリクエストに使用されているのと同じ資格情報で、SFTP サイトにログインします。
1. ルートディレクトリの下の `.ssh` という名前のフォルダーに移動し（存在しない場合はこのフォルダーを作成します）、`authorized_keys` ファイルをそこに配置します。

1. Data Warehouseリクエストをまだ実行していない場合は、 [レポートの送信先の設定リクエストのData Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md).
