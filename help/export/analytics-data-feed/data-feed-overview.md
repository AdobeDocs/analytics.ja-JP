---
description: Web サイトやモバイルアプリケーションから収集されたり、Web サービス API またはデータソースを使用してアップロードされたりしたデータの処理されてアドビの Data Warehouse でに格納されます。この生のクリックストリームデータは、Adobe Analytics で使用されるデータセットとして形成されています。
keywords: クリックストリーム、データフィード、データフィード、データフィード
title: Analytics データフィードの概要
feature: Data Feeds
exl-id: 2cfff9ad-cdb5-4ae9-a266-4f3d3d046f0c
source-git-commit: f66cc6252ecd54c143c08be1e0e7e5bf90cc42e9
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 87%

---

# Analytics データフィードの概要

データフィードは、Adobe Analytics から生データを取得するための強力な方法です。この生データは、アドビ以外の他のプラットフォームで使用し、組織の裁量で使用できます。データは、各時間の終了時に時間単位のバッチで、または毎日の終わりに日単位のバッチで配信されます。

## 前提条件

データフィードを使用する前に、次の要件をすべて満たしていることを確認してください。

* アドビのデータ収集サーバーにデータを送信する実装。詳しくは、 [実装の検証と公開](/help/implement/launch/validate-publish-prod.md) 」を参照してください。
* アカウントが Analytics 製品管理者であるか、アカウントがデータフィードへのアクセス権を持つ製品プロファイルに属している。
* Amazon S3、Google Cloud Platform、Azure RBAC、Azure SAS で設定されたバケット。
* ( レガシー：レガシー FTP および SFTP の宛先タイプの場合のみ必要 )FTP サイトと資格情報（組織から提供される FTP 資格情報）が手元にある。

## 推奨されるデータフィードリソース

1. Adobe ID の資格情報を使用して [experiencecloud.adobe.com](https://experiencecloud.adobe.com) にログインします。
2. 右上の 9 つの正方形のアイコン、色付きの Analytics ロゴの順にクリックします。
3. 上部ナビゲーションバーで、管理者／データフィードに移動します。
4. 「[!UICONTROL 追加]」をクリックします。新しいページで[!UICONTROL フィード情報]、[!UICONTROL 宛先]、[!UICONTROL データ列の定義]の 3 つの主要カテゴリが表示されます。
5. [!UICONTROL フィード情報]フィールドに入力します。
   * 名前：任意の名前（「テストデータフィード」など）。
   * レポートスイート：目的のレポートスイートを選択します。
   * 完了時に電子メールを送信：電子メールを入力します。
   * フィード間隔：目的の間隔（時間単位または日単位）を選択します。
   * 遅延処理：]遅延なし[!UICONTROL のままにできます。
   * 開始日と終了日：数日前から開始日を選択し、今日を終了日として選択します。
6. [!UICONTROL 宛先]フィールドに入力します。
   * タイプ：FTP
   * ホスト：目的の FTP リンク先 URL を入力します。例：`ftp://ftp.omniture.com`。
   * パス：空白のままにします
   * ユーザー名：FTP サイトにログインするためのユーザー名を入力します。
   * パスワードとパスワードの確認：FTP サイトにログインするためのパスワードを入力します。
7. [!UICONTROL データ列の定義]を入力します。
   * ドロップダウンリストで最新の「すべてのAdobe Columns」テンプレートを選択します。
   * 圧縮形式：Gzip
   * パッケージの種類：複数のファイル
   * マニフェスト：ファイルなし
8. 右上の「[!UICONTROL 保存]」をクリックします。
9. 保存すると、履歴データの処理が開始されます。データが 1 日分の処理を終了すると、ファイルは FTP サイトに配置されます。
10. Windows エクスプローラーまたは専用の FTP クライアントを使用して FTP サイトにログインします。
11. 圧縮データフィードファイルをローカルマシンにダウンロードします。
12. `.tar.gz` ファイル拡張子をサポートするプログラムを使用して、圧縮ファイルを解凍します。
13. スプレッドシートまたはデータベースアプリケーションで `hit_data.tsv` ファイルを開き、その日の生データを確認します。

## 次の手順

データフィードを取得する基本的なワークフローを理解したら、組織内のチームと協力して、生データをデータベースに保存または取り込むことができます。

* [データフィードのベストプラクティス](/help/export/analytics-data-feed/data-feeds-best-practices.md):データフィードの作成と管理のベストプラクティス。
* [データフィードの作成](create-feed.md)：個々のフィールドについて詳しく説明する、データフィード作成の技術的な詳細
* [データフィードの管理](df-manage-feeds.md)：データフィードインターフェイスの操作についての詳細
* [データフィードの内容](c-df-contents/datafeeds-contents.md)：圧縮ファイルの内容について <!-- Is this still the output users can download from the destination? I aske Jun. -->
* [データ列の定義](c-df-contents/datafeeds-reference.md)：使用可能なすべての列の包括的なリスト.
* データフィードインターフェイス操作のビデオ：

  >[!VIDEO](https://video.tv.adobe.com/v/25452/?quality=12)

* データフィード ID を見つける方法に関するビデオ：

  >[!VIDEO](https://video.tv.adobe.com/v/335747/?quality=12)