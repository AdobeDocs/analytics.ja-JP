---
description: アドビでは、Data Warehouse リクエストの SFTP サーバーへの書き出しをサポートしています。
keywords: ftp;sftp
title: SFTP サーバーへの Data Warehouse リクエストの送信
feature: FTP Export
exl-id: 45694647-69ec-45e3-b614-4a936909a338
TQID: https://experienceleague.adobe.com/nBerOKEbILwAK5OyayVgdBPN8vq24kk-DXY6XMT50wg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 258
ht-degree: 78%

---

# SFTP サーバーへの Data Warehouse リクエストの送信

アドビでは、[Data Warehouse リクエストのレポートの宛先を設定する](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)の記事の [SFTP](/help/export/data-warehouse/create-request/dw-request-report-destinations.md#sftp) に記載されているように、SFTP サーバーへの Data Warehouse リクエストの書き出しをサポートしています。

以下の作業が完了していることを確認してください。

* Data Warehouse レポートをリクエストする場合、ポート 22 のみを使用する。
* アドビの `authorized_keys` ファイルが、ログインに使用したユーザーのルートディレクトリ内の `.ssh` ディレクトリにある。
* 接続先が `ftp.omniture.com` ではないこと。 Adobeの内部サーバー間のSFTP プロトコルはサポートされていません。
* 宛先は、一要素（PKI）認証をサポートしています。 2要素の課題がある場合、レポートの配信は失敗します。 サーバーが二要素認証を試行するように設定されていないことを確認してください。 Adobe Analyticsでは、キーのみが必要であり、ログインには他の何も使用されません。
* AdobeはSSHv2暗号化をサポートしており、SSHv1にフォールバックします（RSA キーのみ）。

Data Warehouse リクエストを SFTP 経由で正常に送信するには：

1. [Data Warehouse リクエストのレポート先の設定](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)の記事にある、[SFTP](/help/export/data-warehouse/create-request/dw-request-report-destinations.md#sftp) に記載されている手順に従います（公開鍵のダウンロードを含む）。
1. Data Warehouse リクエストに使用されているのと同じ資格情報で、SFTP サイトにログインします。
1. ルートディレクトリの下の `.ssh` という名前のフォルダーに移動し（存在しない場合はこのフォルダーを作成します）、`authorized_keys` ファイルをそこに配置します。

1. Data Warehouse リクエストをまだ完了していない場合は、[Data Warehouse リクエストのレポート先の設定](/help/export/data-warehouse/create-request/dw-request-report-destinations.md).の説明に従って完了します。
