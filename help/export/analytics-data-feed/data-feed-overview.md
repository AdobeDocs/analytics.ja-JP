---
description: データフィードを使用してAdobe Analyticsから生データを取得する方法を説明します。 データフィードを使用するための前提条件を確認します。次に何を行うかを説明します。
keywords: クリックストリーム、データフィード、データフィード、データフィード
title: Analytics データフィードの概要
feature: Data Feeds
exl-id: 2cfff9ad-cdb5-4ae9-a266-4f3d3d046f0c
source-git-commit: 08e29da4847e8ef70bd4435949e26265d770f557
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 79%

---

# Analytics データフィードの概要

データフィードは、Adobe Analytics から生データを取得するための強力な方法です。この生データは、アドビ以外の他のプラットフォームで使用し、組織の裁量で使用できます。データは、各時間の終了時に時間単位のバッチで、または毎日の終わりに日単位のバッチで配信されます。

## 前提条件

データフィードを使用する前に、次の要件をすべて満たしていることを確認してください。

* アドビのデータ収集サーバーにデータを送信する実装。実装ユーザーガイドの[実装の検証と公開](/help/implement/launch/validate-publish-prod.md)を参照してください。
* アカウントが Analytics 製品管理者であるか、アカウントがデータフィードへのアクセス権を持つ製品プロファイルに属している。
* Amazon S3、Google Cloud Platform、Azure RBAC、Azure SAS で設定されたバケット。
* （レガシー：レガシー FTP および SFTP の宛先タイプにのみ必要）FTP サイトと資格情報が手元にある（FTP 資格情報は組織が提供）。

## 次の手順

以下のリソースは、データフィードを取得する基本的なワークフローを理解するのに役立ちます。基本的なワークフローを理解したら、組織内のチームと協力して、生データをデータベースに保存または取り込むことができます。

* [データフィードのベストプラクティス](/help/export/analytics-data-feed/data-feeds-best-practices.md)：データフィードの作成と管理のベストプラクティス。
* [データフィードの作成](create-feed.md)：個々のフィールドについて詳しく説明する、データフィード作成の技術的な詳細
* [データフィードの管理](df-manage-feeds.md)：データフィードインターフェイスの操作についての詳細
* [ データフィードの内容 ](c-df-contents/datafeeds-contents.md)：圧縮ファイル <!-- Is this still the output users can download from the destination? I aske Jun. --> ージ内の内容を理解する
* [データ列の定義](c-df-contents/datafeeds-reference.md)：使用可能なすべての列の包括的なリスト.

>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [ データフィードインターフェイスの操作 ](https://video.tv.adobe.com/v/3428564?quality=12&learn=on&captions=jpn){target="_blank"} を参照してください。

>[!ENDSHADEBOX]



>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [ データフィード ID を見つける ](https://video.tv.adobe.com/v/335747?quality=12&learn=on){target="_blank"} を参照してください。

>[!ENDSHADEBOX]
