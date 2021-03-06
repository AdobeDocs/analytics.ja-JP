---
description: 課金ページでは、各レポートスイートのトラフィックの詳細を含む課金情報にアクセスできます。承認された管理者のみがこのページにアクセスできます。
title: 課金
feature: Admin Tools
exl-id: cea802e4-99c4-491e-99c2-8476870001f7
source-git-commit: 2c0aef13bdb88b0a7aa9f100c72c21f66a14c8dd
workflow-type: ht
source-wordcount: '503'
ht-degree: 100%

---

# 課金

課金ページでは、各レポートスイートのトラフィックの詳細を含む課金情報にアクセスできます。承認された管理者のみがこのページにアクセスできます。

>[!NOTE]
>
>「課金」タブへのアクセスが無効な場合、アカウントマネージャーにご連絡ください。

課金ページのトラフィック概要データでは、レポートに表示されるページビュー数のデータと請求書に表示される課金対象サーバーコールとの関係を示します。[!UICONTROL 課金]ページを使用すると、次のことを実行できます。

* 請求書を監査します。
* 内部会計の配分用にレポートスイート別にコストを分割します。
* プライマリおよびセカンダリサーバーコールの配分を表示します。

[!UICONTROL 課金]ページで月別に情報をまとめます。

月別のトラフィック概要データを表示するには、トラフィックデータを表示したい月を指定して、「**[!UICONTROL 表示]**」をクリックします。

表示される[!UICONTROL 月別の請求]レポートには次のような情報があります。

| 列 | 説明 |
|--- |--- |
| レポートスイート | レポートスイートはデータ収集アクティビティに関連しています。 |
| 場所 | レポートスイートデータを格納するデータセンター：サンホセ（カリフォルニア州）、ダラス（テキサス州）、太平洋岸北西部（米国）、ロンドン（英国）、シンガポール。ほとんどの場合、すべての会社のレポートスイートは同じデータセンター内にあります。 |
| プライマリサーバーコール | Web サイト訪問者のブラウザーまたは Data Insertion API から直接受け取った要求です。プライマリヒット（ページビュー）、プライマリカスタムイベント、プライマリダウンロードイベントおよびプライマリ終了イベントが含まれます。 |
| セカンダリサーバーコール | 複数のスイートのタグによって作成されたか、Vista ルールによってコピー／移動されたプライマリサーバーコールのコピーです。セカンダリサーバーコールが Vista ルールによって別のレポートスイートに（コピーではなく）移動した場合、この移動は請求ページでは負の数で示されます。この例では、セカンダリコールの合計数がプライマリサーバーコール数から引かれます。 |
| サーバーコール総数 | 特定の場所にあるレポートスイートの、プライマリサーバーコールとセカンダリサーバーコールの合計です。 |
| ページビュー数 | 各レポートスイートのページビューの合計数です。サイト指標／ページビュー数でページビューの値を確認できます。 |
| ダウンロード | 各レポートスイートのダウンロードの合計数です。サイトのコンテンツ／リンク／ファイルのダウンロード数でダウンロードの値を確認できます。 |
| カスタムリンク | 各レポートスイートのカスタムリンクの合計数です。サイトのコンテンツ／リンク／カスタムリンクでカスタムリンクの値を確認できます。 |
| 離脱リンク | 各レポートスイートの離脱リンクの合計数です。サイトのコンテンツ／リンク／離脱リンクで離脱リンクの値を確認できます。 |

>[!NOTE]
>
>[!UICONTROL 月別の請求]レポートの作業用コピーを取得するには、クリップボードにコピーしてから Microsoft Excel&#42; などのスプレッドシートプログラムに貼り付けます。

## レポート日と処理日 {#section_51A48C2F223F4904BE1407C13333C457}

レポートユーザーインターフェイスでは、データは常に&#x200B;**レポート日**&#x200B;と一緒に表示されます。レポート日は、イベントに関連付けられたタイムスタンプです。

一方、使用状況／課金では、常に&#x200B;**処理日**&#x200B;を使用します。処理日は、データがシステムで実際に処理された日です。通常は、基本的な遅延、データのインポート、またはイベントのタイムゾーンの違いにより（すべて太平洋時間で処理されます）、レポート日と処理日は完全には一致しません。
