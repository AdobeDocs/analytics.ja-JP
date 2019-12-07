---
description: アドビは、SFTPサーバーへのData Warehouseリクエストのエクスポートをサポートしています。
keywords: ftp;sftp
title: SFTP サーバーへの Data Warehouse リクエストの送信
uuid: 393634a1-0643-4d63-bb6e-fb80f1ba76c1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# SFTP サーバーへの Data Warehouse リクエストの送信

アドビは、SFTPサーバーへのData Warehouseリクエストのエクスポートをサポートしています。

以下の作業を行います。

アドビは、次の条件が満たされている場合に、SFTPサーバーへのData Warehouseリクエストのエクスポートをサポートします。

* [!DNL sftp://] プロトコルがホストフィールド(例： [!DNL sftp://ftp.example.com])で指定され、Data Warehouseレポートをリクエストする際にポート22のみが使用されます。

   このオプションは、以下に説 [!DNL sftp+norename://] 明するように使用することもできます。

* Adobe's [!DNL authorized_keys] file is in the [!DNL .ssh] directory within the root directory of the user you log in with

* 接続先が [!DNL ftp.omniture.com] ではないこと。アドビの内部サーバー間では、SFTP プロトコルはサポートされていません。
* 接続先で、1 要素（PKI）認証がサポートされていること。2 要素のチャレンジがある場合、レポートの配信は失敗します。2 要素認証を試行するようにサーバーが設定されていないことを確認してください。Adobe Analytics では、ログインに鍵のみを使用し、その他のものは使用しません。
* アドビでは、SSHv2 暗号化をサポートしています。SSHv2 が使用できない場合は、SSHv1 を使用します（RSA 鍵のみ）。

To successfully send a [!DNL Data Warehouse] request via SFTP:

1. 組織のサポート対象ユーザーがカスタマーケアに連絡して、[!DNL authorized_keys] ファイルを入手します。
1. このファイルを入手したら、[!DNL Data Warehouse] リクエストで使用されているものと同じ資格情報で FTP サイトにログインします。
1. In the root directory, navigate to the folder named [!DNL .ssh] (if one does not exist, create one) and place the [!DNL authorized_keys] file there.

1. Go to the [!DNL Data Warehouse] request manager. Configure the request as desired, then click **[!UICONTROL Advanced Delivery Options]**.

1. In the pop-up window, click **[!UICONTROL FTP]**, then specify the ftp site (including the [!DNL sftp://] protocol, such as [!DNL sftp://ftp.omniture.com]) via port 22.

   Including the [!DNL sftp://] protocol is only permitted when using SFTP. Regular FTP requests should omit the protocol prefix (such as, [!DNL ftp.omniture.com] instead of [!DNL ftp://ftp.omniture.com]).

1. 「フォルダー」フィールドに、ファイルを配置するフォルダーの名前を入力します。フォルダーは必須です。
1. 手順 2 と同じユーザー名とパスワードを入力します。
1. Click **[!UICONTROL Send]**.

SFTP の PUT コマンドを使用すると、指定したディレクトリに、.part という拡張子の一時ファイルが配置されます。アップロードが完了すると、ファイルの拡張子が最終的な拡張子に変更され、その時点でファイルが使用できるようになります。

Alternatively, [!DNL sftp+norename://] can be specified instead of [!DNL sftp://] to upload the file directly with the final name, without a temporary [!DNL .part] file name during upload. この方法は、SFTPサーバーがアップロード中にファイル名の変更を自動的に処理し、アップロードが完了する前にファイルが処理される可能性がない場合に適しています。
