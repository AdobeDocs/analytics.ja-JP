---
description: Java 11でAd Hoc Analysisを実行する方法について説明します。
seo-description: Java 11でAd Hoc Analysisを実行する方法について説明します。
seo-title: Ad Hoc AnalysisおよびJava 11
title: Java 11 で Ad Hoc Analysis を実行する
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# Java 11 で Ad Hoc Analysis を実行する

Java 11 で Ad Hoc Analysis を実行する際には、Java 8 の場合と異なる追加手順に従う必要があります。

## 前提条件

IT チームと協力して、以下を確認してください。

* Java 11 must be installed, with *JAVA_HOME* environment variable set
* *PATH_TO_FX_SDK* 環境変数が JavaFX SDK ディレクトリを示すよう設定して、JavaFX をインストールする必要があります。例えば、Mac の場合は *PATH_TO_FX_SDK=/homedir/javafx-sdk-11.0.2*、PC の場合は *PATH_TO_FX_SDK=C:\Users\username\javafx-sdk-11.0.2* となります。

## Java 11 用 Ad Hoc Analysis をインストールする

1. **[!UICONTROL Analytics/ツール/Ad Hoc Analysisに移動します]**。
1. Click **[!UICONTROL Ad Hoc Analysis (Java 11)]**. これにより、zip ファイルがダウンロードされます。
1. ダウンロードしたファイルを展開します。
1. **.bat（PC）または.sh（Mac）ファイルを選択します**。Adobe Analytics URLの次の「sc」の番号を確認して、適切なデータセンターファイルを選択します。 (3 = LON, 4 = SIN, 5 = PNW) PCを使用する場合は、「PCについて」に移動して、32-bitと64-bitのWindowsオペレーティングシステムのどちらを実行しているかを確認します。 次に、適切な .bat ファイルを選択します。
1. **選択したファイルを実行します**。PCの場合：.bat　ファイルをダブルクリックします。Mac の場合、.sh ファイルを右クリックしてから、「**[!UICONTROL このアプリケーションで開く／その他... ／ユーティリティ／（すべてのアプリケーションを有効にする）／ターミナルを選択／開く]**」を選択します。
1. Ad Hoc Analysis にログインします。

> [!NOTE] Federated IDとEnterprise IDの認証方法は、Ad Hoc AnalysisのJava 11バージョンと互換性がありません。

## Ad Hoc Analysis　（Java 11）でサポートされていない機能

Ad Hoc Analysisと互換性のあるJava 11バージョンには、いくつかの既知の制限があります。

* Federated ID および Enterprise ID 認証方式はサポートされていません。
* Linux オペレーティングシステムはサポートされていません。
* When using a Mac, do not use the Mac application menu (including *cmd + Q*). 使用した場合、Ad Hoc Analysis が警告なしに終了する可能性があります。代わりに、Ad Hoc Analysis 内のメニューを使用してください。
* MacOS で Ad Hoc Analysis を実行している場合、サイト分析ビジュアライゼーションはサポートされません。

## FAQ

**質問：「\bin\javawが見つかりません」というエラー（以下の例）が表示されます。どうすればよいですか。**

![](/help/analyze/ad-hoc-analysis/assets/error-java.png)

A：このエラーが発生した場合は、IT チームと協力し、Java 11 で Ad Hoc Analysis を実行するために必要な *JAVA_HOME* 環境変数を設定してください。
