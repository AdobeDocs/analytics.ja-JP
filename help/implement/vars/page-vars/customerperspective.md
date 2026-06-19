---
title: customerPerspective
description: アプリが前景または背景にあるときにモバイルアプリのヒットが発生したかどうかを指定します。
feature: Appmeasurement Implementation
role: Admin, Developer
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 199
ht-degree: 0%

---

# customerPerspective

`customerPerspective`変数は、アプリが前景または背景にあるときにモバイルアプリのヒットが発生したかどうかを指定します。 Adobe データ コレクションに`cp` クエリ パラメーターとして送信され、[&#x200B; ヒット タイプ &#x200B;](/help/components/dimensions/hit-type.md) ディメンションに入力されます。

## 有効な値

`customerPerspective`は次の文字列値を受け入れます。

* `foreground`: アプリがアクティブ使用中にヒットが発生しました。
* `background`: アプリがバックグラウンドで実行されている間に、場所の更新やプッシュ通知によってトリガーされたヒットなどが発生しました。

## この変数の設定方法

Adobe Mobile SDK（バージョン 4.13.6以降）は、自動的に`customerPerspective`を設定します。通常、手動で設定することはありません。 AppMeasurementを通じてブラウザーから送信されたヒット数は、常に`foreground`と報告されます。 変数がヒットから欠落している場合、そのヒットはフォアグラウンドヒットとして扱われます。

## レポートへの影響

前景/背景の区別は、訪問の処理方法に影響します。

* 訪問は、少なくとも1つのフォアグラウンドヒットが含まれている場合にのみカウントされます。
* バックグラウンドヒットは、コンバージョンイベントに引き続き関連付けることができ、仮想レポートスイートの[&#x200B; コンテキスト対応セッション &#x200B;](/help/components/vrs/vrs-mobile-visit-processing.md)を通じて分析できます。 このビヘイビアーは、プッシュ通知の有効性を測定する場合に便利です。
