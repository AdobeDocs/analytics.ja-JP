---
description: Java11でAd Hoc Analysisを実行する方法について説明します。
seo-description: Java11でAd Hoc Analysisを実行する方法について説明します。
seo-title: Ad Hoc AnalysisおよびJava11
title: Java11でAd Hoc Analysisを実行する
translation-type: tm+mt
source-git-commit: 23bdb0c24416c376ec1df7b609a5794dbf8886f2

---


# Java11でAd Hoc Analysisを実行する

Java 11 で Ad Hoc Analysis を実行する際には、Java 8 の場合と異なる追加手順に従う必要があります。

## 前提条件

IT チームと協力して、以下を確認してください。

* *JAVA_ HOME* 環境変数を設定するには、Java11をインストールする必要があります
* *PATH_TO_FX_SDK* 環境変数が JavaFX SDK ディレクトリを示すよう設定して、JavaFX をインストールする必要があります。例えば、Mac の場合は *PATH_TO_FX_SDK=/homedir/javafx-sdk-11.0.2*、PC の場合は *PATH_TO_FX_SDK=C:\Users\username\javafx-sdk-11.0.2* となります。

## Java 11 用 Ad Hoc Analysis をインストールする

1. **[!UICONTROL Analytics/ツール/Ad Hoc Analysisに移動]**&#x200B;します。
1. **[!UICONTROL "Ad Hoc Analysis（Java11）」をクリック]**&#x200B;します。これにより、zip ファイルがダウンロードされます。
1. ダウンロードしたファイルを展開します。
1. **.bat（PC）または.sh（Mac）ファイルを選択します**。Adobe Analytics の URL の「sc」に続く数字を確認し、適切なデータセンターファイルを選択します。（3= LON、4= SEN、5= PNGW） PCを使用する場合は、"PCについて」に移動して、32ビットまたは64ビットのWindowsオペレーティングシステムを実行しているかどうかを確認します。次に、適切な .bat ファイルを選択します。
1. **選択したファイルを実行します**。PCの場合：.bat　ファイルをダブルクリックします。Mac の場合、.sh ファイルを右クリックしてから、「**[!UICONTROL このアプリケーションで開く／その他... ／ユーティリティ／（すべてのアプリケーションを有効にする）／ターミナルを選択／開く]**」を選択します。
1. Ad Hoc Analysis にログインします。

>[!Ntoo]
>
> Federated IDおよびEnterprise ID認証方法は、Ad Hoc AnalysisのJava11バージョンと互換性がありません。

## Ad Hoc Analysis　（Java 11）でサポートされていない機能

Ad Hoc Analysisと互換性があるJava11バージョンには、いくつかの既知の制限があります。

* Federated ID および Enterprise ID 認証方式はサポートされていません。
* Linux オペレーティングシステムはサポートされていません。
* When using a Mac, do not use the Mac application menu (including *cmd + Q*). 使用した場合、Ad Hoc Analysis が警告なしに終了する可能性があります。代わりに、Ad Hoc Analysis 内のメニューを使用してください。
* MacOS で Ad Hoc Analysis を実行している場合、サイト分析ビジュアライゼーションはサポートされません。

## FAQ

**Q:"Unable find\ bin\ javaw"エラー（下記の例）-何をすればよいか。**

![](/help/analyze/ad-hoc-analysis/assets/error-java.png)

A：このエラーが発生した場合は、IT チームと協力し、Java 11 で Ad Hoc Analysis を実行するために必要な *JAVA_HOME* 環境変数を設定してください。