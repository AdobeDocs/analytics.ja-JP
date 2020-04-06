---
description: アドビがどのようにしてデータソースへのアクセスを実現しているかに関する情報です。
subtopic: Data sources
title: データソースの仕組み
topic: Developer and implementation
uuid: ee9e6e74-9b00-4733-9a4b-d9f2b954cc7c
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# データソースの仕組み

アドビがどのようにしてデータソースへのアクセスを実現しているかに関する情報です。

>[!NOTE]データソースからデータが送信されると、インポートされたデータは、他のメソッド（JavaScript ビーコン、ActionSource、Data Insertion API など）で収集されたレポートデータと区別がつかなくなります。データをインポートした後に削除することはできません。

![](assets/data_sources_overview.png)

データの送信には、次の2つの方法があります。

* [FTP](/help/import/c-data-sources/datasrc-how-data-sources-works.md#section_0E70022648F94061AF5B4AD6C7145243)
* [API](/help/import/c-data-sources/datasrc-how-data-sources-works.md#section_65DACC9CE00C437BBFDD02D19C25A4BD)

## FTP {#section_0E70022648F94061AF5B4AD6C7145243}

マーケティングレポートを通じてFTPベースのデータソースを作成および管理できます。このレポートでは、FTPファイル転送を使用してデータファイルをデータソースにインポートします。 データソースを作成すると、アドビからFTPの場所が提供され、この場所を使用してデータソースファイルをアップロードできます。 アップロードが完了すると、データソースは自動的に検索し、処理します。 処理が完了すると、データをマーケティングレポートで使用できるようになります。

## API {#section_65DACC9CE00C437BBFDD02D19C25A4BD}

アドビのオファーは、アプリケーションをデータソースにプログラム的にリンクすることを可能にするデータソースAPIです。 これにより、中間のFTPサーバーを必要とせず、HTTP、SOAP、REST経由でデータを転送できます。

データソ [ースAPIドキュメントを参照](https://github.com/AdobeDocs/analytics-1.4-apis/tree/master/docs/data-sources-api)。
