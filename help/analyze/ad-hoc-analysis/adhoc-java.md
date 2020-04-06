---
description: Java 11 で Ad Hoc Analysis を実行する方法について説明します。
title: Java 11 で Ad Hoc Analysis を実行する
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Java 11 で Ad Hoc Analysis を実行する

Java 11を使用してAd Hoc分析を実行する場合は、Java 8を使用して実行する場合と比較して、追加の手順に従う必要があります。

## 前提条件

ITチームと協力して、次の事項を確実に実施します。

* *JAVA_HOME* 環境変数を設定して Java 11 をインストールする必要があります。
* JavaFXをインストールし、 *PATH_TO_FX_SDK* 環境変数がJavaFX SDKディレクトリを指すようにする必要があります。 例えば、 *PATH_TO_FX_SDK=/homedir/javafx-sdk-11.0.2（Macの場合）または* PATH_TO_FX_SDK=C:\Users\username\javafx-sdk-11.0.2 ** （PCの場合）です。

## Java 11用アドホック分析のインストール

1. **[!UICONTROL Analytics > Tools > Ad Hoc Analysis]** にアクセスします。
1. クリック **[!UICONTROL Ad Hoc Analysis (Java 11)]**. これでzipファイルがダウンロードされます。
1. ダウンロードしたファイルを解凍します。
1. **.bat(PC)または.sh(Mac)ファイルを選択します**。 Adobe Analytics の URL の「sc」に続く数字を確認し、適切なデータセンターファイルを選択します。（3 = LON, 4 = SIN, 5 = PNW）PC を使用している場合は、「バージョン情報」に進んで、実行中の Windows オペレーティングシステムが 32 ビット版か 64 ビット版のどちらでのあるかを確認してください。次に、適切な.batファイルを選択します。
1. **選択したファイルを実行します**。 PCの場合：.bat ファイルをダブルクリックします。Macの場合：.shファイルを右クリックし、を選択しま **[!UICONTROL Open With > Other... > Utilities > (Enable all applications) > select Terminal > Open]**&#x200B;す。
1. Ad Hoc Analysis にログインします。

>[!NOTE]Federated ID および Enterprise ID 認証方式は、Java 11 バージョンの Ad Hoc Analysis とは互換性がありません。

## Ad Hoc Analysis （Java 11）でサポートされていない機能

Ad Hoc Analysis 互換 Java 11 バージョンには、いくつか既知の制限事項があります。

* Federated IDおよびEnterprise IDの認証方法はサポートされていません。
* Linuxオペレーティングシステムはサポートされていません。
* Mac を使用するときは、Mac のアプリケーションメニュー（*cmd + Q* を含む）を使用しないでください。これにより、アドホック分析が警告なしで閉じる場合があります。 代わりに、Ad Hocメニュー内の分析を使用します。
* サイト分析のビジュアライゼーションは、MacOSでアドホック分析を実行する場合はサポートされません。

## FAQ

**Q：「\ bin \ javaw が見つかりません」というエラーが表示されます（下記の例）。どうすればいいですか？**

![](/help/analyze/ad-hoc-analysis/assets/error-java.png)

A：このエラーが発生した場合は、IT チームと協力し、Java 11 で Ad Hoc Analysis を実行するために必要な *JAVA_HOME* 環境変数を設定してください。
