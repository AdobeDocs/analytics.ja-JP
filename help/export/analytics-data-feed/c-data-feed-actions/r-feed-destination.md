---
description: 「フィード宛先」セクションは、フィードの配信方法を定義します。
keywords: データフィード;フィード;destination;sftp;s3;ftp;settings
seo-description: 「フィード宛先」セクションは、フィードの配信方法を定義します。
seo-title: フィード宛先
solution: Analytics
title: フィード宛先
uuid: 4a59e8de- e7a6-4f7a- bf42- db7d59e61b4c
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# フィード宛先

「フィード宛先」セクションは、フィードの配信方法を定義します。

次の 4 つの配信チャネルがあります。

* FTP
* SFTP
* Amazon S3
* Azure BLOB

## FTP {#section_D2B521C49BDE4F91A1999FE222CF306F}

データフィードのデータは、アドビまたは顧客のホストする FTP の場所に配信できます。

顧客のホストする FTP サーバーにデータをアップロードする場合は、該当するユーザー名、パスワード、アップロードパスをアドビに提供する必要があります。アドビ側ではサーバーのデータの削除をおこなわないため、お客様側でディスクスペースを管理する独自のプロセスを実装する必要があります。

![](assets/dest-ftp.jpg)

## SFTP {#section_8D9215E441474D2BBC56228C2BC926E5}

データフィードのデータは、アドビまたはお客様がホストする SFTP の場所に配信できます。

お客様がホストする FTP サーバーにデータをアップロードする場合は、該当するユーザー名およびアップロードパスをアドビに提供する必要があります。

<!-- 

Adobe Customer Care will provide you with a Public key. Verify in recording.

 -->

アドビ側ではサーバーのデータの削除をおこなわないため、お客様側でディスクスペースを管理する独自のプロセスを実装する必要があります。

![](assets/dest-sftp.jpg)

## Amazon S3 {#section_4191CD7B8D3F419EB850B286B542C14A}

Amazon S3 バケットにファイルをアップロードできます。Amazon は、（Amazon サーバー上で）保存データを自動的に暗号化します。データをダウンロードすると、自動的に復号化されます。

Amazon S3 を使用してデータをアップロードする場合、バケット名、アクセスキー ID、シークレットキーおよびフォルダー名を提供する必要があります。

![](assets/dest-s3.jpg)

データフィードは、次の 11 の標準 AWS リージョンと通信します（必要に応じて、適切な署名アルゴリズムを使用）。

* us-east-1
* us-west-1
* us-west-2
* ap-south-1
* ap-northeast-2
* ap-southeast-1
* ap-southeast-2
* ap-northeast-1
* eu-central-1
* eu-west-1
* sa-east-1

現在、中国（北京）AWS リージョン（cn-north-1）はサポートしていません。

## Azure BLOB {#section_1E9F1D0E7EAB4189A5D748FCA57D63D1}

Azure BLOB にファイルをアップロードできます。

![](assets/azure.png)

## フィールド {#section_AD54B41BC7C945DC85F5FB8FCD4A4792}

次の表に、すべての配信チャネルのすべてのオプションを示します。使用できるオプションは、選択した配信チャネルによって異なります。

<table id="table_F743C620C82349D9943A13B99EA312BA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> フィールド </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>アクセスキー </p> </td> 
   <td colname="col2"> <p>Amazon S3 アクセスキーを入力します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>グループ </p> </td> 
   <td colname="col2"> <p>Amazon S3 バケットの場所を入力します。 </p> <p>この値は、適切な S3 バケット形式に合致する必要があります。(See <a href="https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html" format="html" scope="external"> https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html</a>.) </p> <p> <p>注意：Amazon S3 の設定について詳しくは、後述の <a href="../../../export/analytics-data-feed/feed-troubleshooting.md#section_6797EBBB7E6D44D4B00C7AEDF4C2EE1D" format="dita" scope="local">Amazon S3 データフィードの BucketOwnerFullControl 設定</a>を参照してください。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>コンテナ </p> </td> 
   <td colname="col2"> <p>Azure BLOB コンテナ名を入力します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> ホスト </p> </td> 
   <td colname="col2"> <p>FTP または SFTP ホストの場所を指定します。 </p> <p>この値は、適切な FTP/SFTP 形式（<code>ftp.domain.com/subdomain</code> または <code>sftp.domain.com/subdomain</code>）に準拠する必要があります。 </p> <p> FTP および SFTP の標準ポート 21 および 22 が必要です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>パスワード </p> <p>パスワードを確認 </p> </td> 
   <td colname="col2"> <p>FTP パスワードを入力します。確認するために再入力します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>パス </p> </td> 
   <td colname="col2"> <p>ホストまたはバケットへのパスを選択します。このパスは、フィード作成前に存在している必要があります。 </p> <p> <p>注意：Amazon S3 の設定について詳しくは、後述の <a href="../../../export/analytics-data-feed/feed-troubleshooting.md#section_6797EBBB7E6D44D4B00C7AEDF4C2EE1D" format="dita" scope="local">Amazon S3 データフィードの BucketOwnerFullControl 設定</a>を参照してください。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>アカウント </p> </td> 
   <td colname="col2"> <p> Azure ストレージアカウントを入力します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>公開鍵 </p> </td> 
   <td colname="col2"> <p>SFTP 公開鍵を指定します。 </p> <p>公開鍵をダウンロードして SFTP リポジトリを設定する必要があります。 </p> <p> <p>注意：フィードを作成するために公開鍵をダウンロードする必要はありません。 </p> </p> <p>以前のフィードの作成時に既にダウンロード済みの公開鍵を使用できます。 </p> <p>詳しくは、<a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/ftp/ftp_sftp_dw.html" format="html" scope="external">https://marketing.adobe.com/resources/help/ja_JP/whitepapers/ftp/ftp_sftp_dw.html</a> を参照してください。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>キー </p> <p>キーを確認 </p> </td> 
   <td colname="col2"> <p> ストレージアクセスキーを入力します。確認のために再入力します。 </p> <p> <p>注意：アクセスキーへのアクセスについては、<a href="https://docs.microsoft.com/en-us/azure/storage/common/storage-create-storage-account#view-and-copy-storage-access-keys" format="https" scope="external">https://docs.microsoft.com/ja-JP/azure/storage/common/storage-create-storage-account#view-and-copy-storage-access-keys</a> を参照してください。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>シークレットキー </p> <p>シークレットキーを確認 </p> </td> 
   <td colname="col2"> <p>S3 シークレットキーを入力します。確認するために再入力します。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>タイプ </p> </td> 
   <td colname="col2"> <p>送信先のタイプを選択します。 </p> <p> 
     <ul id="ul_B893EEDA73A34DE0AEB8570BE9027F21"> 
      <li id="li_325546FCEB404C50AA6829573CCA340B">FTP（デフォルト） </li> 
      <li id="li_6A2C03115903484797485D073A610607">AmazonS3 </li> 
      <li id="li_C24540F6FCD24702B7693A515CEBE977">SFTP </li> 
      <li id="li_8E03CA78E7FE427C9F6F8B112BC76266">Azure BLOB </li> 
     </ul> </p> <p>送信先のタイプを選択すると、フィールドのリストが変更されて、選択した送信先に使用可能なオプションが反映されます。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ユーザー名 </p> </td> 
   <td colname="col2"> <p>FTP ユーザー名を入力します。 </p> </td> 
  </tr> 
 </tbody> 
</table>

