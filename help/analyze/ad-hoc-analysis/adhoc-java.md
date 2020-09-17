---
description: Java 11 で Ad Hoc Analysis を実行する方法について説明します。
title: Java 11 で Ad Hoc Analysis を実行する
translation-type: tm+mt
source-git-commit: d4cb2acb4ecaecce3644a2f3cf29913440e5cd6a
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 97%

---


# Java 11 で Ad Hoc Analysis を実行する

>[!IMPORTANT]
>
>Adobeは、2021年3月1日にAd Hoc Analysisを廃業に移す予定です。 [詳細情報...](https://adobe.ly/discoverworkspace).

Java 11 で Ad Hoc Analysis を実行する際には、Java 8 の場合と異なる追加手順に従う必要があります。

## 前提条件

IT チームと協力して、以下を確認してください。

* *JAVA_HOME* 環境変数を設定して Java 11 をインストールする必要があります。
* *PATH_TO_FX_SDK* 環境変数が JavaFX SDK ディレクトリを示すよう設定して、JavaFX をインストールする必要があります。例えば、Mac の場合は *PATH_TO_FX_SDK=/homedir/javafx-sdk-11.0.2*、PC の場合は *PATH_TO_FX_SDK=C:\Users\username\javafx-sdk-11.0.2* となります。

## Java 11 用 Ad Hoc Analysis をインストールする

1. **[!UICONTROL Analytics ／ツール／Ad Hoc Analysis]** に移動します。
1. 「**[!UICONTROL Ad Hoc Analysis (Java 11)]**」をクリックします。これにより、zip ファイルがダウンロードされます。
1. ダウンロードしたファイルを展開します。
1. **.bat（PC）または.sh（Mac）ファイルを選択します**。Adobe Analytics の URL の「sc」に続く数字を確認し、適切なデータセンターファイルを選択します。（3 = LON, 4 = SIN, 5 = PNW）PC を使用している場合は、「バージョン情報」に進んで、実行中の Windows オペレーティングシステムが 32 ビット版か 64 ビット版のどちらでのあるかを確認してください。次に、適切な .bat ファイルを選択します。
1. **選択したファイルを実行します**。PC の場合：.bat ファイルをダブルクリックします。Mac の場合、.sh ファイルを右クリックしてから、「**[!UICONTROL このアプリケーションで開く／その他... ／ユーティリティ／（すべてのアプリケーションを有効にする）／ターミナルを選択／開く]**」を選択します。
1. Ad Hoc Analysis にログインします。

>[!NOTE]
>
>Federated ID および Enterprise ID 認証方式は、Java 11 バージョンの Ad Hoc Analysis とは互換性がありません。

## Ad Hoc Analysis （Java 11）でサポートされていない機能

Ad Hoc Analysis 互換 Java 11 バージョンには、いくつか既知の制限事項があります。

* Federated ID および Enterprise ID 認証方式はサポートされていません。
* Linux オペレーティングシステムはサポートされていません。
* Mac を使用するときは、Mac のアプリケーションメニュー（*cmd + Q* を含む）を使用しないでください。使用した場合、Ad Hoc Analysis が警告なしに終了する可能性があります。代わりに、Ad Hoc Analysis 内のメニューを使用してください。
* MacOS で Ad Hoc Analysis を実行している場合、サイト分析ビジュアライゼーションはサポートされません。

## FAQ

**Q：「\ bin \ javaw が見つかりません」というエラーが表示されます（下記の例）。どうすればいいですか？**

![](/help/analyze/ad-hoc-analysis/assets/error-java.png)

A：このエラーが発生した場合は、IT チームと協力し、Java 11 で Ad Hoc Analysis を実行するために必要な *JAVA_HOME* 環境変数を設定してください。
