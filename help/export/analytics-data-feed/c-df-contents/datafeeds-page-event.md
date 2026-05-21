---
description: ページイベントに基づいてヒットタイプを判定するルックアップテーブル。
keywords: ページ;イベント;page_event;post_page_event
title: ページイベント参照
feature: Data Feeds
exl-id: ef0467df-b94b-4cec-b312-96d8f42c23b0
TQID: https://experienceleague.adobe.com/QAGYKNnpMl2tM6BRux7BBL-YFpMTgUIXsHT-9bGKWnA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 226
ht-degree: 100%

---

# ページイベント参照

`page_event` の値に基づいてヒットタイプを判定するルックアップテーブル。 [データ列リファレンス](datafeeds-reference.md)に記載されているように、`page_event` 列と `post_page_event` 列は tinyint unsigned です。

* AppMeasurement と Web SDK のページビュー呼び出しの実装について詳しくは、[`t()`](/help/implement/vars/functions/t-method.md) を参照してください。
* AppMeasurement と Web SDK のリンクトラッキング呼び出しの実装について詳しくは、[`tl()`](/help/implement/vars/functions/tl-method.md) を参照してください。
* Adobe Analytics で XDM ペイロードをページイベントタイプに変換する方法について詳しくは、[Adobe Experience Platform Edge Network を使用した Adobe Analytics の実装](/help/implement/aep-edge/overview.md)を参照してください。

| `page_event` の値 | `post_page_event` の値 | 説明 |
| --- | --- | --- |
| `0` | `0` | すべての標準ページビュー呼び出し。 これは、ほとんどのヒットのデフォルト値です。 |
| `10` | `100` | カスタムリンク。 リンクタイプを `o`（AppMeasurement）に設定するか、`xdm.web.webInteraction.type` を `other`（Web SDK または Mobile SDK）に設定します。 |
| `11` | `101` | ダウンロードリンク。 リンクタイプを `d`（AppMeasurement）に設定するか、`xdm.web.webInteraction.type` を `download`（Web SDK または Mobile SDK）に設定します。 |
| `12` | `102` | 離脱リンク。 リンクタイプを `e`（AppMeasurement）に設定するか、`xdm.web.webInteraction.type` を `exit`（Web SDK または Mobile SDK）に設定します。 |
| `31` | `76` | メディアの開始 |
| `32` | `77` | メディアの更新（他の変数処理なし） |
| `33` | `78` | メディアの更新（他の変数処理あり） |
| `40` | `80` | 調査 |
| `50` | `50` | ストリーミングメディアの開始 |
| `51` | `51` | ストリーミングメディアのクローズ |
| `52` | `52` | ストリーミングメディアのスクラビング |
| `53` | `53` | ストリーミングメディアのキープアライブ |
| `54` | `54` | ストリーミングメディア広告の開始 |
| `55` | `55` | ストリーミングメディア広告のクローズ |
| `56` | `56` | ストリーミングメディア広告のスクラビング |
| `60` | `60` | Primetime メディアの開始 |
| `61` | `61` | Primetime メディアのクローズ |
| `62` | `62` | Primetime メディアのスクラビング |
| `63` | `63` | Primetime メディアのキープアライブ |
| `64` | `64` | Primetime メディア広告の開始 |
| `65` | `65` | Primetime メディア広告のクローズ |
| `66` | `66` | Primetime メディア広告のスクラビング |
| `70` | `70` | Target アクティビティデータを含む |
