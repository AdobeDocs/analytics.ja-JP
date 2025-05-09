---
description: ページイベントに基づいてヒットのタイプを判断するためのルックアップテーブル。
keywords: ページ；イベント；page_event;post_page_event
title: ページイベント参照
feature: Data Feeds
exl-id: ef0467df-b94b-4cec-b312-96d8f42c23b0
source-git-commit: e16b0d7b3fe585dc8e9274a77833ad5af3c63124
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 4%

---

# ページイベント参照

`page_event` 値に基づいてヒットのタイプを判断する参照テーブル。 [ データ列リファレンス ](datafeeds-reference.md) に記載されているように、`page_event` 列と `post_page_event` 列は tinyint unsigned です。

* AppMeasurementと web SDKのページビュー呼び出しの実装について [`t()`](/help/implement/vars/functions/t-method.md) しくは、「ページビュー呼び出しの実装」を参照してください。
* AppMeasurementと Web SDKのリンクトラッキングコールの実装について理解するには、[`tl()`](/help/implement/vars/functions/tl-method.md) を参照してください。
* Adobe Analyticsで XDM ペイロードをページイベントタイプに変換する方法については、[Adobe Experience Platform Edge Networkを使用したAdobe Analyticsの実装 ](/help/implement/aep-edge/overview.md) を参照してください。

| `page_event` の値 | `post_page_event` の値 | 説明 |
| --- | --- | --- |
| `0` | `0` | すべての標準ページビュー呼び出し。 これは、ほとんどのヒットのデフォルト値です。 |
| `10` | `100` | カスタムリンク。 リンクタイプを `o` （AppMeasurement）に設定するか、`xdm.web.webInteraction.type` を `other` （web SDKまたはモバイル SDK）に設定します。 |
| `11` | `101` | ダウンロードリンク。 リンクタイプを `d` （AppMeasurement）に設定するか、`xdm.web.webInteraction.type` を `download` （web SDKまたはモバイル SDK）に設定します。 |
| `12` | `102` | 離脱リンク。 リンクタイプを `e` （AppMeasurement）に設定するか、`xdm.web.webInteraction.type` を `exit` （web SDKまたはモバイル SDK）に設定します。 |
| `31` | `76` | メディア開始 |
| `32` | `77` | メディアの更新（他の変数処理なし） |
| `33` | `78` | メディアの更新（他の変数処理を使用） |
| `40` | `80` | 調査 |
| `50` | `50` | ストリーミングメディア開始 |
| `51` | `51` | ストリーミングメディアを閉じる |
| `52` | `52` | ストリーミングメディアスクラビング |
| `53` | `53` | ストリーミングメディアのキープアライブ |
| `54` | `54` | ストリーミングメディア広告の開始 |
| `55` | `55` | ストリーミングメディア広告の終了 |
| `56` | `56` | ストリーミングメディアとスクラビング |
| `60` | `60` | Primetime メディア開始 |
| `61` | `61` | Primetime メディアクローズ |
| `62` | `62` | Primetime メディアスクラブ |
| `63` | `63` | Primetime メディアはキープアライブします |
| `64` | `64` | Primetime メディアと開始 |
| `65` | `65` | Primetime メディアとクローズ |
| `66` | `66` | Primetime メディアとスクラブ |
| `70` | `70` | Target アクティビティデータを含む |
