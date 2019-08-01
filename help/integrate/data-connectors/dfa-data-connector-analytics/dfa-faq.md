---
description: 'null'
keywords: DFA
seo-description: 'null'
seo-title: よくある質問
solution: Analytics
title: よくある質問
topic: Data Connectors
uuid: 59d187e9-1ec1-4cf3-8831- b981f87c9372
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# よくある質問{#frequently-asked-questions}

## Why won’t the Data Connectors wizard accept my login credentials? {#section-f019b3de18774df3954af7881aa564fa}

ログイン資格情報が有効であることが検証済みの場合、次に、統合に提供されたユーザー名が API アクセスで有効であることを検証します。Data Connectors ウィザードは、DFA API を使用してログイン資格情報を検証し、DFA API のアドビ特有の設定のオフとオンを切り替えます。API アクセスは、管理者によって DFA インターフェイス内からオンにする必要がある設定です。次に、ウィザードで選択した広告主 ID または Floodlight 設定 ID へのアクセス権があることを確認します。

## 夜間にアップロードした指標（DFA インプレッション数、DFA クリック数など）からのデータが表示されないのはなぜですか。 {#section-465fd22ae6b447ffb6baf20b57daa433}

統合のバージョン 1.5 を使用している場合は、統合がまだ顧客サイト ID を割り当てられていないことが原因である可能性があります。顧客サイト ID（CSID）は、夜間に交換が発生する場合や、DFA 広告サーバーからデータをリクエストする場合に必要です。CSID は、統合が Google と交換される日から最大 3 日かかります。CSID を Google から受け取ると、最新の JavaScript コードと共に、統合の新しい CSID の電子メールアドレスから通知されます。

3 日以上過ぎてもセットアップ電子メールが届かず、指標が表示されない場合、CSID が既に別の統合に割り当てられていることが問題である可能性があります。Google は、CSID とレポートスイートの間で 1 対1 のマッピングを維持します。つまり、あるレポートスイートの統合で、別のレポートスイートの別の統合と同じ広告主 ID を使用している場合、最初の統合にだけ CSID が割り当てられます。CSID がマッピングされるレポートスイートまたは広告主 ID を変更するには、Google Support でチケットを開く必要があります。

例えば、レポートスイート A の統合に CSID を割り当てられた広告主 ID Z があるとします。後で別の統合が広告主 Z のレポートスイート B にセットアップされる場合、この新しい統合には CSID が再割り当てされません。この場合、Google チケットが必要になります。一方、レポートスイート A、広告主 ID Z の例では、後にレポートスイート A の別の統合は、広告主 Z がセットアップされ、最初の統合のみが統合のデータを受け取りますが、この場合、最初の統合を非アクティブ化すれば、2 番目の統合にデータを流すことができます。

>[!NOTE]
>
>CSIDは、統合のバージョン2.0では使用されないので、CSIDネゴシエーションプロセスは適用されません。

## 統合の 2.0 を使用していますが、DFA 広告のコスト指標が表示されません。なぜですか。 {#section-805748111bbe4bbf918d6dbbb2641fff}

コスト指標は、Data Connectors ウィザードで有効にすると同時に、Google DFA 側から有効にして、DFA インターフェイスで提供する必要があります。最初に、DFA メディアコストの Analytics イベントをマッピングし、通貨コードが指定されているかを確認します。メディアコストイベントをマッピングし、ウィザードを終了して保存済みの場合、DFA API で DFA omnitureCostData フラグがオンになります。これは、指標が夜間にファイルを送付する必要があるという Google へのシグナルです。omnitureCostData が有効になっている DFA インターフェイスを使用して、統合 Floodlight のプロパティを調べることで、再確認できます。最後に、これらの 2 か所をチェックした後、統合 Floodlight の一部である広告でコストデータおよびコスト構造が指定されていることを確認します。コストデータが DFA インターフェイスで指定されていない場合、Analytics に表示されません。

## 特定の広告で DFA インプレッション数またはビュースルーが表示されず、クリック数およびクリックスルーが表示されるのはなぜですか。 {#section-39b2eeeefd7f43d1a373df0b987bacef}

一部の広告には、クリックトラッカーと呼ばれる、クリックデータのみを記録するものがあります。このタイプの広告は、Floodlight サーバーがクエリされてから、最後のインプレッションデータを返しません。特定の広告がクリックトラッカーやクリックのみの広告であるかどうかを検証するには、DFA の代理店または Google Support 担当者に問い合わせてください。

## DFA クリック数を表示する広告にクリックスルーがないのはなぜですか。 {#section-758c1f1fc5b54bfc9294dcdc71bbd96a}

この質問には多くの回答があります。

第 1 に、問題の広告にランディングページの URL があり、それが（a）違いを表示している同じレポートスイートの Adobe コードでタグ付けされ、（b）*`clickThroughParam`* クエリ文字列パラメーターを含んでいることをチェックします。

Second, verify that you have a working integration by following through the steps in [Confirming a Successful DFA Integration](../dfa-data-connector-analytics/dfa-integration/dfa-confirm-integration.md#concept-c1c869d2a6fa46b09fe41fc286e407c6). DFA トラッキングコードがランディングページの Adobe ヒットを使用して表示されている場合、クリックスルーは DFA キャンペーンレポートで表示する必要があります。表示されない場合、レポートスイートがランディングページの *`s.account`* 変数で一致し、Reports &amp; Analytics でレポートスイートが表示されるかを確認します。これらが一致する場合、ビュースルー eVar レポートのトラッキングコードが DFA:XXX:XXX:XXX:llXXX:XXX:XXX:XXX:XXX のようになっているかをチェックします。

これらは、DFA から生データを要約する DFA VISTA ルールにエラーがあることを示します。この問題は、アドビのアカウント担当者を通じてサポートチケットを開くことで改善できます。If none of the solutions above explain the problem, see [Reconciling Metric Discrepancies](../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies/dfa-reconciling-metric-discrepancies.md#concept-8c31ebe761ca4b3fab1e3a18ef5d098f) to explore other possibilities