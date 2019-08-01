---
description: 'null'
keywords: DFA
seo-description: 'null'
seo-title: 前提条件
solution: Analytics
title: 前提条件
topic: Data Connectors
uuid: b5f5e30c- e269-41a4-9236-5ddc404bfd94
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# 前提条件{#prerequisites}

DFA 用の Adobe Data Connectors 統合を開始する前に、以下をおこないます。

* 統合のバージョン 1.5 に対して統合するか、またはバージョン 2.0 を待つかを決定します。この決定は、DFA アカウントでどの機能を使用するかや、統合する期間によって決まります。詳しくは、[バージョン 2.0 について](../dfa-data-connector-analytics/dfa-version-differences.md#concept-2c7d6a6ab8524dccad96ea0c17228664)を参照してください。
* DFA 広告主をどのように Adobe Analytics レポートスイートにマッピングするかを決定します。例えば、複数の DFA 広告主と複数のレポートスイートがある場合、どの広告主とどのレポートスイートをペアにするかを決定する必要があります。
* データコレクションコードのバージョン H.22 以降を使用して、Adobe データコレクションコードをトラッキングするすべてのページに実装します。
* 統合する Floodlight 設定の一部である DFA アカウントの広告主 ID を確認します。統合は、Floodlight 設定内にあるすべての広告主を自動的にインポートします。
* DFA アカウントのユーザー名とパスワードを確認します。
* 各 DFA 広告主を 1 つの Adobe Analytics レポートスイートにのみ関連付けます。複数のレポートスイートへのタグ付けは、DFA 用のデフォルトの Genesis 統合ではサポートされません。
* クリックスルークエリ文字列パラメーターを、統合の一部となる各 DFA プレースメントのランディングページに追加します。このクエリ文字列パラメーターは、クリックスルーを適切にカウントするために必要です。
* 複数のドメインを経由して訪問者をリダイレクトしないように DFA プレースメントを設定します。例えば、マイクロサイトが別のサイト、www.fgh.com にリダイレクトされる場合、プレースメントは、応答者を www.xyz.com でホストされているマイクロサイトに転送しないようにする必要があります。キャンペーンの反応が複数のドメインにわたる場合、クリックスルーデータやビュースルーデータが水増しされ、誤った結果になる可能性があります。
* キャンペーン情報を保持する Reports &amp; Analytics のカスタム変数を特定します。
* DFA ビュースルー情報を格納する Reports &amp; Analytics eVar を特定します。この eVar は、この DFA 統合にのみ使用します。
* インプレッション数およびクリック数データを格納する Reports &amp; Analytics イベントを特定します。これらのイベント名は適宜変更できます。
* （オプション）DFA コストデータを格納する Reports &amp; Analytics イベントを特定します。これらのイベント名は適宜変更できます。
* （オプション）DFA エラーおよびタイムアウトを格納する Reports &amp; Analytics カスタム変数および成功イベントを特定します。これらの変数は、統合で起こりうる問題を診断するのに役立ちます。
* （オプション）DFA 用の Data Connectors 統合に関連する情報および通知を受信するための特別な電子メールアカウントを作成します。

