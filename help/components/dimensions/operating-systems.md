---
title: オペレーティングシステム
description: 訪問者のオペレーティングシステム。
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
source-git-commit: 26de81f090cebb45473a04a2edbe281f1c8591a4
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 29%

---

# オペレーティングシステム

「オペレーティングシステム」ディメンションは、訪問者が使用していたオペレーティングシステムとバージョンを示します。Web プロパティに OS 固有の機能がある場合、このディメンションは、最も一般的なオペレーティングシステムを示します。

## このディメンションへのデータ入力

このディメンションは、Adobe 内部のルックアップテーブルを参照します。ルックアップ値は、イメージリクエストの `User-Agent` HTTP ヘッダーに基づきます。AppMeasurement ライブラリ（Adobe Experience Platform のタグを介した場合など）を使用する場合、このディメンションは初期設定の状態で動作します。

## ディメンション項目

ディメンション項目には、訪問者が使用するオペレーティングシステムが含まれます。例として、`"Windows 10"`、`"OS X 10.15"`、および `"Android 9"` があります。

## ラベル設定と定義の変更

以下に、ユーザーエージェントとAdobe Analyticsのレポートでオペレーティングシステムがどのように表示されたかに関する具体的な問題を示します。

### Appleオペレーティングシステムの命名規則の変更：

バージョン 11 以降では、Mac OS の代わりに OS X を使用して、Appleオペレーティングシステムを参照します。

例：

* macOSバージョン10.15.7(UA 文字列でのバージョン10.15.7の表示に関する以下の注意を参照 )。
* OS X バージョン 11.0.0

### Mac OS のバージョンが、バージョン10.15.7以降のユーザーエージェントで正しくありません 

2023 年 1 月以降、すべてのブラウザーのユーザーエージェントで、Mac OS のバージョンが10.15.7（新しいバージョンでも）と表示されます。 これは、UA にバージョン 11 を含めると、明らかに一部のウェブサイトで問題が発生したためです。 また、Appleは、UA に誤った OS バージョンを含めると、プライバシーに関する利点があると述べています。

クライアントヒントは、プラットフォームのバージョンヒント (「Sec-CH-UA-Platform-Version」) に正しいバージョンが含まれていることに注意してください。 これは高エントロピーのヒントなので、Adobeでは自動的に収集されません。 詳しくは、 [Adobe Analyticsヒント FAQ](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=en) 高エントロピーのヒントを収集する方法の詳細

### Windows 11 以降のユーザーエージェントで、Windows のバージョンが正しくありません

2023 年 1 月以降、すべてのブラウザーの User Agent では、Windows 11 が Windows 10 と表示されます。

クライアントヒントは、プラットフォームのバージョンヒント (「Sec-CH-UA-Platform-Version」) に正しいバージョンが含まれていることに注意してください。 これは高エントロピーのヒントなので、Adobeでは自動的に収集されません。 詳しくは、 [Adobe Analyticsヒント FAQ](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=en) 高エントロピーのヒントを収集する方法の詳細
