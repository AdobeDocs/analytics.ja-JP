---
description: DFA の Data Connectors 統合は、Analytics 変数を使用して DFA キャンペーン結果をトラッキングします。
keywords: DFA
seo-description: DFA の Data Connectors 統合は、Analytics 変数を使用して DFA キャンペーン結果をトラッキングします。
seo-title: Analytics 変数とイベント
solution: Analytics
title: Analytics 変数とイベント
topic: Data Connectors
uuid: 8996cb58-c793-4600-99ef-af3064642b29
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# Analytics 変数とイベント{#analytics-variables-and-events}

DFA の Data Connectors 統合は、Analytics 変数を使用して DFA キャンペーン結果をトラッキングします。

キャンペーン変数以外に、ユーザーにとって意味のある Analytics イベントおよび eVar を使用できます。この DFA 統合で使用するイベントおよび eVar を特定したら、Analytics 管理コンソールを使用してそれらを有効にできます。統合変数は、DFA 統合をアクティブ化する前に有効にする必要があります。次の表に、DFA 統合に必要な Analytics 変数を示します。

| 変数 | わかりやすい名前 | セット方法 | 説明 |
|---|---|---|---|
| s.campaign または eVar | 広告トラッキングコード | Data Connector によって DFA キャンペーン用に自動的に設定されます。 | すべてのキャンペーンのクリックスルーコンバージョンをトラッキングします。 |
| eVar* | ビュースルー | VISTA および DFA によって DFA キャンペーン用に自動的に設定されます。 | DFA ID のビュースルーデータをトラッキングします。この eVar は、 *`s.campaign`* variable. 変数プロバイダーIDで識別されたのと同じコンバージョン変数である必要があります。 eVar で、完全な下位関係が有効になっていることを確認します。この機能を有効にするためのコストは、Data Connectors 統合の費用に含まれています。 |
| eVar* | DFA クエリエラー | （オプション）JavaScript コレクションコードを使用して設定されます。 | DFAから返されたいくつかのエラーコードの1つを含みます。 |
| event* | ビュースルー数 | Data Connector によって DFA キャンペーン用に自動的に設定されます。 | ユーザーが広告を表示して、クリックスルーはせずにサイトに到達した回数をキャプチャします。 |
| event* | インプレッション数 | DFA からのデータフィードによって自動的に設定されます。 | 特定の DFA 広告が提供された回数をトラッキングします。 |
| event* | クリック数 | DFA からのデータフィードによって自動的に設定されます。 | ユーザーが特定の DFA バナー広告をクリックした回数をトラッキングします。この指標は、いくつかの理由のうちの 1 つによって、ネイティブの Analytics クリックスルー指標と比較して異なる数が生じる可能性があります。詳しくは、[指標の不一致の調整](/help/import/data-connectors/dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies.md)を参照してください。 |
| event* | DFA タイムアウト | （オプション）JavaScript コレクションコードを使用して設定されます。 | DFAが&#x200B;*`s.maxDelay`* がタイムアウトする前に、DFA が応答に失敗した回数をカウントします。これは、DFA 導入に問題があるかどうかを判断するのに役立ちます。 |
| event* | DFA メディアコスト | DFA からのデータフィードによって自動的に設定されます。 | DFA インターフェイスに入力されたメディアコスト指標を含めます。これらの指標を表示するために、この機能は、DFA 側で有効にする必要があります。 |

*未使用の eVar またはカスタムイベントを選択します。
