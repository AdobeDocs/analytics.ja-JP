---
description: DFA の Data Connectors 統合は、Analytics 変数を使用して DFA キャンペーン結果をトラッキングします。
keywords: DFA
seo-description: DFA の Data Connectors 統合は、Analytics 変数を使用して DFA キャンペーン結果をトラッキングします。
seo-title: Analytics 変数とイベント
solution: Analytics
title: Analytics 変数とイベント
topic: Data Connectors
uuid: 8996cb58- c793-4600-99ef- af3064642b29
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Analytics 変数とイベント{#analytics-variables-and-events}

DFA の Data Connectors 統合は、Analytics 変数を使用して DFA キャンペーン結果をトラッキングします。

キャンペーン変数以外に、ユーザーにとって意味のある Analytics イベントおよび eVar を使用できます。この DFA 統合で使用するイベントおよび eVar を特定したら、Analytics 管理コンソールを使用してそれらを有効にできます。統合変数は、DFA 統合をアクティブ化する前に有効にする必要があります。次の表に、DFA 統合に必要な Analytics 変数を示します。

| 変数 | わかりやすい名前 | セット方法 | 説明 |
|---|---|---|---|
| s.campaign または eVar | 広告トラッキングコード | Data Connector によって DFA キャンペーン用に自動的に設定されます。 | すべてのキャンペーンのクリックスルーコンバージョンをトラッキングします。 |
| eVar* | ビュースルー | VISTA および DFA によって DFA キャンペーン用に自動的に設定されます。 | DFA ID のビュースルーデータをトラッキングします。この eVar は、*`s.campaign`* 変数を使用します。Must be the same conversion variable as identified in the Variable Provider ID (See [Update Your Website’s Data Collection Code](../dfa-data-connector-analytics/dfa-integration/dfa-web-site-updates/dfa-update-data-collection-code.md#concept-8c108723ea0b4cc9a8c5cdc2d05894e3)). eVar で、完全な下位関係が有効になっていることを確認します。この機能を有効にするためのコストは、Data Connectors 統合の費用に含まれています。 |
| eVar* | DFA クエリエラー | （オプション）JavaScript コレクションコードを使用して設定されます。 | DFA から返されたいくつかのエラーコードのいずれかが含まれます（これらのエラーコードのリストについては、[統合の設定](../dfa-data-connector-analytics/dfa-integration/dfa-integration.md#concept-cf33e1051c73452cbd26e950d0293858)の表を参照）。 |
| event* | ビュースルー数 | Data Connector によって DFA キャンペーン用に自動的に設定されます。 | ユーザーが広告を表示して、クリックスルーはせずにサイトに到達した回数をキャプチャします。 |
| event* | インプレッション数 | DFA からのデータフィードによって自動的に設定されます。 | 特定の DFA 広告が提供された回数をトラッキングします。 |
| event* | クリック数 | DFA からのデータフィードによって自動的に設定されます。 | ユーザーが特定の DFA バナー広告をクリックした回数をトラッキングします。この指標は、いくつかの理由のうちの 1 つによって、ネイティブの Analytics クリックスルー指標と比較して異なる数が生じる可能性があります。詳しくは、[指標の不一致の調整](../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies/dfa-reconciling-metric-discrepancies.md#concept-8c31ebe761ca4b3fab1e3a18ef5d098f)を参照してください。 |
| event* | DFA タイムアウト | （オプション）JavaScript コレクションコードを使用して設定されます。 | DFAが&#x200B;*`s.maxDelay`* がタイムアウトする前に、DFA が応答に失敗した回数をカウントします。これは、DFA 導入に問題があるかどうかを判断するのに役立ちます。 |
| event* | DFA メディアコスト | DFA からのデータフィードによって自動的に設定されます。 | DFA インターフェイスに入力されたメディアコスト指標を含めます。これらの指標を表示するために、この機能は、DFA 側で有効にする必要があります。 |

*未使用の eVar またはカスタムイベントを選択します。
