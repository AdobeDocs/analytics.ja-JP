---
description: 新しいポータルなどのコンテンツを集積する Web サイト用の共通設定を定義します。
title: 集積ポータル
feature: Report Suite Settings
exl-id: 48f57f27-289c-4e26-9fb2-e34d48c1f2e6
TQID: https://experienceleague.adobe.com/rH1TSHrMMKxFtMlv0GR-UKF-OJk8SBbt1pq92DYhgVk
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
ht-degree: 70%

---

# 集積ポータル

新しいポータルなどのコンテンツを集積する Web サイト用の共通設定を定義します。

| コンバージョン変数 | タイプ | 下位関係 | 配分 | 有効期限 | `s_code` 変数 |
|---|---|---|---|---|---|
| 内部キャンペーン | 文字列 | 基本一致 | 最新 (最後) | 訪問 | `evar1` |
| 内部検索キーワード | 文字列 | 基本一致 | 最新 (最後) | 訪問 | `evar2` |
| 紹介カテゴリ | 文字列 | 基本一致 | 最新 (最後) | 訪問 | `evar3` |

| 成功イベント | タイプ | `s_code` 変数 |
|---|---|---|
| ログイン | カウンタ (下位関係なし) | `event1` |
| リファラルビュー | カウンタ (下位関係なし) | `event2` |
| リファラルクリック | カウンタ (下位関係なし) | `event3` |

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
