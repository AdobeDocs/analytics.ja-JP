---
description: 'null'
seo-description: 'null'
seo-title: Windows Phone 8
solution: Analytics, Experience Cloud
subtopic: リリースノート
title: Windows Phone 8
topic: 開発者と実装
uuid: 7378969a-d219-42bf-9750-141acc9e4b7d
translation-type: ht
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Windows Phone 8{#windows-phone}

>[!NOTE]
>
>ライブラリの現在のバージョンを検索するには、デバッグログを有効にしてください。

モバイルライブラリの[ダウンロード](https://marketing.adobe.com/developer/ja/get-started/mobile/c-measuring-mobile-applications)は [!DNL Developer Connection] で入手できます。

>[!NOTE]
>
>[!DNL Windows] Phone 8 SDK は、[Windows 8.1 ユニバーサルアプリストア](../appmeasurement-release-notes/c-release-notes-winu.md) SDK で置き換えられます。今後、この SDK の開発はおこなわれません。

## バージョン 3.0.4 {#section_51A8A53CDFB24F6F9D882E9C30ECDB49}

リリース日：**2013 年 8 月 22 日**

* コンテキストデータのキーにアンダースコアを使用できるようになりました。

## バージョン 3.0.5 {#section_DFE58939E33C447FBBF8B04E612A96B5}

リリース日：**2013 年 5 月 23 日**

* バグが修正され、パフォーマンスが改善されました。

## バージョン 3.0.4 {#section_F303B6E5955248CF8BDA6C7CB994BAD5}

リリース日：**2013 年 4 月 19 日**

* 以前のセッションの長さが誤って計算されることがある問題を修正しました。

## バージョン 3.0.3 {#section_0159586C3EC94865A485A8E586862DF6}

リリース日：**2013 年 3 月 22 日**

* `DateTime` オブジェクトに関するローカライゼーションの問題を修正しました。

## バージョン 3.0.2 {#section_296C375729EA4474BDF3FD6ADD4BEAFB}

リリース日：**2013 年 2 月 27 日**

* `ADMS_Measurement.visitorID` にデフォルト値があらかじめ設定されるようになりました。
* キャッシュから自動応答が発生することがある問題を修正しました。

## バージョン 3.0.1 {#section_5865E881249441ADBB03A9637548650F}

リリース日：**2013 年 2 月 22 日**

* 非推奨だった `offlineThrottleDelay` の設定は、スレッドの最適化によって不要になりました。この設定は後方互換性のために引き続き保持されますが、効果は何もありません。
* `DayOfWeek` が他のプラットフォームで収集される値と同じ 1-base の日曜始まりになりました。
* アプリケーションがときどきクラッシュする原因となっていたオフラインストレージの問題を修正しました。

