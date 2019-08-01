---
description: appFiguresのdata connectors統合では、Analytics変数を使用して様々なappFigures指標を追跡します。
seo-description: appFiguresのdata connectors統合では、Analytics変数を使用して様々なappFigures指標を追跡します。
seo-title: Analytics統合変数
title: Analytics統合変数
uuid: 08d5b714-1c97-4be6- aae8-1f8192535425
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Analytics Integration Variables{#analytics-integration-variables}

appFiguresのdata connectors統合では、Analytics変数を使用して様々なappFigures指標を追跡します。

次の表に、appFigures統合用に自動的にアクティブ化されるAnalytics変数を示します。

## Required Variables {#section-3ca8dc46bab0436cba0c9ef827c8356a}

>[!NOTE]
>
>この統合では、アプリケーションストアデータに専用の変数を使用するので、カスタムコマース変数やイベントを割り当てる必要はありません。

| 変数の種類 | 名前 | セット方法 | 説明 |
|---|---|---|---|
| eVar | App Store オブジェクト ID | appFiguresからインポートしました。 | このeVarを訪問の有効期限、最新の配分、基本サブリレーションで設定します。 |
| event（数値） | App Store でのダウンロード数 | appFiguresからインポートしました。 | モバイルアプリケーションダウンロード数。 |
| event（数値） | App Store購入（アプリ内） | appFiguresからインポートしました。 | アプリ内課金および購読数。 |
| event（数値） | App Store ランク | appFiguresからインポートしました。 | 平均appFigures計算指標を定義するために使用します。直接使用されません。 |
| event（数値） | App Store Rank Divisor | appFiguresからインポートしました。 | 平均appFigures計算指標を定義するために使用します。直接使用されません。 |
| event（数値） | App Store 評価 | appFiguresからインポートしました。 | 平均appFigures計算指標を定義するために使用します。直接使用されません。 |
| event（数値） | App Store 評価の基準値 | appFiguresからインポートしました。 | 平均appFigures計算指標を定義するために使用します。直接使用されません。 |
| event（currency） | App Store売上高（アプリ内） | appFiguresからインポートしました。 | アプリケーション内の売上高からストア費用を引いた値。 |
| event（currency） | App Store売上高（オフ） | appFiguresからインポートしました。 | アプリ購入からの合計売上高は、ストア料金から引いて算出されます。 |
| event（currency） | App Storeロイヤルティ（アプリ内） | appFiguresからインポートしました。 | 未使用 |
| event（currency） | App Storeロイヤルティ（オフ） | appFiguresからインポートしました。 | 未使用 |

