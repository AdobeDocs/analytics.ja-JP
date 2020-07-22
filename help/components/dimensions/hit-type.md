---
title: ヒットタイプ
description: ヒットがフォアグラウンドヒットかバックグラウンドヒットかを判定します。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 2%

---


# ヒットタイプ

「ヒットのタイプ」ディメンションは、ヒットがアドビのデータ収集サーバーに送信されたときに、モバイルアプリがフォアグラウンドかバックグラウンドかを決定します。 このディメンションは、モバイルアプリケーション用のデータを含むレポートスイートにのみ関連します。 AppMeasurementで収集されたブラウザーデータは、常に「フォアグラウンド」としてヒットをレポートします。

## このディメンションにデータを入力する

このディメンションは、バージョン4.13.6以降でのすべてのモバイルSDK実装で初期設定のまま機能します。 モバイルSDKを使用しない場合、「Foreground」ディメンション項目以下のすべてのヒットリスト。 If &quot;Disable Legacy Reporting and Attribution for Background Hits&quot; is checked, then background hits will show up only in [Virtual report suites](../vrs/vrs-mobile-visit-processing.md).

## ディメンション項目

ディメンション項目には、 `"Foreground"` およびが含まれ `"Background"`ます。 モバイルアプリケーションのバックグラウンドで送信されなかったヒットは、ディメンション項目に属し `"Foreground"` ます。 モバイルアプリがバックグラウンドにあった場所に送信されたヒットが、ディメンション項目に属していま `"Background"` す。
