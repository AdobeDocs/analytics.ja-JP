---
title: ヒットタイプ
description: ヒットがフォアグラウンドヒットかバックグラウンドヒットかを判定します。
translation-type: tm+mt
source-git-commit: 1869d69566d26aa7d99c520efc2e835901439d48
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 2%

---


# ヒットタイプ

「ヒットのタイプ」ディメンションは、ヒットがアドビのデータ収集サーバーに送信されたときに、モバイルアプリがフォアグラウンドかバックグラウンドかを決定します。 このディメンションは、モバイルアプリケーション用のデータを含むレポートスイートにのみ関連します。 AppMeasurementで収集されたブラウザーデータは、常に「フォアグラウンド」としてヒットをレポートします。

## このディメンションにデータを入力する

このディメンションは、バージョン4.13.6以降でのすべてのモバイルSDK実装で初期設定のまま機能します。 モバイルSDKを使用しない場合、「Foreground」ディメンション値以下のすべてのヒットリスト。 If &quot;Disable Legacy Reporting and Attribution for Background Hits&quot; is checked, then background hits will show up only in [Virtual report suites](../vrs/vrs-mobile-visit-processing.md).

## 分析コード値

ディメンション値には、 `"Foreground"` およびが含まれ `"Background"`ます。 モバイルアプリケーションのバックグラウンドで送信されなかったヒットは、すべて `"Foreground"` ディメンション値に属します。 モバイルアプリがバックグラウンドにあった場所に送信されたヒットが、ディメンション値に属し `"Background"` ます。
