---
description: eコマース web サイトの共通設定を定義します。
title: コマース
feature: Report Suite Settings
exl-id: 90e5d446-10b8-4d40-8bd0-8b13e1c2f603
TQID: https://experienceleague.adobe.com/l1-8tv-5dvKi4rx9-2tRoN4hK9ROr-ajWgKm0uFggrI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
subfeature_v2:
  - id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 188
ht-degree: 69%

---

# コマース

eコマース web サイトの共通設定を定義します。

| コンバージョン変数 | タイプ | 下位関係 | 配分 | 有効期限 | `s_code` 変数 |
|---|---|---|---|---|---|
| 内部プロモーション | 文字列 | 基本一致 | 最新 (最後) | 訪問 | `evar1` |
| 内部検索キーワード | 文字列 | 基本一致 | 最新 (最後) | 訪問 | `evar2` |
| マーチャンダイジングカテゴリー | 文字列 | 基本一致 | 最新 (最後) | 訪問 | `evar3` |
| Commerce Variable 4 | 文字列 | 基本一致 | 最新 (最後) | 訪問 | `evar4` |
| Commerce Variable 5 | 文字列 | 基本一致 | 最新 (最後) | 訪問 | `evar5` |

| 成功イベント | タイプ | `s_code` 変数 |
|---|---|---|
| 登録 | カウンタ (下位関係なし) | `event1` |
| カスタムイベント 1～5 | カウンタ (下位関係なし) | `event1, event2, event3, event4, event5` |

| カスタムインサイト変数 | `s_code` 変数 |
|---|---|
| トラフィックプロパティ 1～5 | `prop1, prop2, prop3, prop4, prop5` |

次の表に、標準コマースイベントのリストを示します。 これらのイベントの初期設定は、すべてのレポートスイートテンプレートで同じです。 n/Aのs_code変数を持つイベントは設定する必要がなく、自動的に提供されます。

| 標準Commerce イベント | タイプ | `s_code` 変数 |
|---|---|---|
| 売上高 | カウンタ | `purchase` |
| 注文件数 | カウンタ | `purchase` |
| 単位 | カウンタ | `purchase` |
| 買い物かご | カウンタ | `scOpen` |
| 買い物かご表示 | カウンタ | `scView` |
| インスタンス | カウンタ | 該当なし |
| チェックアウト | カウンタ | `scCheckout` |
| 買い物かごへの追加 | カウンタ | `scAdd` |
| 買い物かごからの削除 | カウンタ | `scRemove` |
| 訪問数 | カウンタ (下位関係なし) | 該当なし |
| ページビュー数 | カウンタ (下位関係なし) | 該当なし |
| 日別ユニーク訪問者 | カウンタ (下位関係なし) | 該当なし |
| ユニーク訪問者 | カウンタ (下位関係なし) | 該当なし |
