---
description: ページイベントに基づいてヒットタイプを判定するルックアップテーブル。
keywords: ページ;イベント;page_event;post_page_event
title: ページイベント参照
feature: Data Feeds
exl-id: ef0467df-b94b-4cec-b312-96d8f42c23b0
source-git-commit: e16b0d7b3fe585dc8e9274a77833ad5af3c63124
workflow-type: ht
source-wordcount: '226'
ht-degree: 100%

---

# ページイベント参照

`page_event` の値に基づいてヒットタイプを判定するルックアップテーブル。[データ列リファレンス](datafeeds-reference.md)に記載されているように、`page_event` 列と `post_page_event` 列は tinyint unsigned です。

* AppMeasurement と Web SDK のページビュー呼び出しの実装について詳しくは、[`t()`](/help/implement/vars/functions/t-method.md) を参照してください。
* AppMeasurement と Web SDK のリンクトラッキング呼び出しの実装について詳しくは、[`tl()`](/help/implement/vars/functions/tl-method.md) を参照してください。
* Adobe Analytics で XDM ペイロードをページイベントタイプに変換する方法について詳しくは、[Adobe Experience Platform Edge Network を使用した Adobe Analytics の実装](/help/implement/aep-edge/overview.md)を参照してください。

| `page_event` の値 | `post_page_event` の値 | 説明 |
| --- | --- | --- |
| `0` | `0` | すべての標準ページビュー呼び出し。これは、ほとんどのヒットのデフォルト値です。 |
| `10` | `100` | カスタムリンク。リンクタイプを `o`（AppMeasurement）に設定するか、`xdm.web.webInteraction.type` を `other`（Web SDK または Mobile SDK）に設定します。 |
| `11` | `101` | ダウンロードリンク。リンクタイプを `d`（AppMeasurement）に設定するか、`xdm.web.webInteraction.type` を `download`（Web SDK または Mobile SDK）に設定します。 |
| `12` | `102` | 離脱リンク。リンクタイプを `e`（AppMeasurement）に設定するか、`xdm.web.webInteraction.type` を `exit`（Web SDK または Mobile SDK）に設定します。 |
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
