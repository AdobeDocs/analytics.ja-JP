---
description: Advertising Analytics に関するよくある質問。
title: 広告分析に関するよくある質問
feature: Advertising Analytics
exl-id: 664a5641-1c79-439f-a9fb-2ff134574412
TQID: https://experienceleague.adobe.com/HC9F-en-nLFRkxsaY6Szdtb3jR5NgdpsbjSAX6kTBlQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: a9364d69-0c51-44bf-8b5f-6d99c04493b8id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c2296997-5d79-4905-b32e-99b5aa892429id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 1298
ht-degree: 10%

---

# よくある質問

## アクセス／権利 {#access}

+++ この機能にアクセスするには、Adobe Advertisingのお客様である必要がありますか？

いいえ。この機能は、Advertising以外のお客様が利用できます。 Adobe Advertisingをご利用のお客様は、既存のAnalyticsとAdvertisingの統合を活用できます。

+++

+++ Advertising Analyticsを使用できるAdobe Analytics SKUはどれですか？ 

Advertising AnalyticsはAdobe Analyticsで利用できます

* [選択](https://www.adobe.com/jp/data-analytics-cloud/analytics/select.html)

* [Prime](https://www.adobe.com/jp/data-analytics-cloud/analytics/prime.html)

* [Ultimate](https://www.adobe.com/jp/data-analytics-cloud/analytics/ultimate.html)

+++

+++ Advertising Analyticsを使用するために追加料金を支払う必要がありますか？ 

いいえ、適切なSKU プロビジョニング以外の場合、Advertising Analyticsには追加費用は発生しません。

+++

+++ Advertising Analyticsはサーバーコールの使用状況に対してカウントされますか？

いいえ。Advertising Analyticsでは、サーバーコールのコストを発生させない特殊なデータソースタイプを使用します。

+++

+++ 既にAdobe Advertisingを使用している場合、Advertising Analytics機能を引き続き使用できますか？

互換性のある検索エンジンアカウントはすべてAdvertising Analyticsに渡され、読み取り専用として表示されます。 編集や更新は、すべてAdvertisingで処理する必要があります。

+++

+++ 正しいSKUを所有していますが、Advertising Analyticsにアクセスできないのはなぜですか？ 

Advertising Analyticsは、Adobe Analytics管理者のみが使用できます。ただし、管理者は管理者以外のユーザーにアクセス権を付与できます。 アクセス権については、管理者にお問い合わせください。

+++

## Advertising Analyticsの使用 {#using}

+++ Advertising Analyticsにはどの検索エンジンアカウントが含まれていますか？

検索エンジンアカウントには、Google AdsとMicrosoft Advertisingが含まれます。

+++

+++ Advertising Analyticsにアクセスするには、どこから行けばよいですか？

Adobe Analyticsにログインした後、[!UICONTROL 管理者]に移動します。 次に、[!UICONTROL Advertising Analytics]を選択して、検索エンジンアカウントを追加します。

+++

+++ データはどのように収集され、Analyticsに渡されますか？ 

Advertising Analyticsでは、一連のカスタム APIを使用して、検索エンジンからAdobe Advertisingにデータを渡し、Adobe Analyticsに渡します。

+++

+++ この統合ではどのような検索データを取得できますか？ 

次のメリットを享受できます。

* インプレッション数
* クリック数
* コスト
* 品質スコア
* 検索エンジンから直接平均位置
* AMO ID インスタンス （クリックインスタンス）

+++

+++ Advertising Analytics データを他のAnalytics データ（指標/ディメンション）で分類できますか？ 

いいえ、生の検索データは独立したデータセットとして取り込まれます。 ただし、クリックデータのインスタンスのバージョンは、他のAnalytics データで分類できます。

+++

+++ アカウントの様々なステータスインジケーター（保留中、アクティブ、一時停止など）の定義を教えてください。 これらのステータスインジケーターは、各検索エンジンアカウントのライフサイクルステージを識別します。 

* [!UICONTROL 保留中]
* [!UICONTROL 一時停止]とは、アカウントが以前に設定されたが、非アクティブ状態になったことを意味します。
* [!UICONTROL  アクティブ ]とは、アカウントが完全に設定され、検索データを引き出していることを意味します。

+++

+++ Advertising Analytics アカウントを特定のレポートスイートにマッピングしようとしていますが、レポートスイートモーダルでは使用できません。 なぜですか？ 

レポートスイートをAdvertising Analytics アカウントに割り当てる前に、目的のレポートスイートをAdvertising Analytics レポート用に[ プロビジョニングする必要があります](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md)
これは、管理者/ レポートスイート / `[select report suite]` / 設定を編集/ Advertising Analytics Configurationからアクセスできる別の管理ページを介して行われます。

+++

+++ バーチャルレポートスイートをAdvertising Analytics アカウントに割り当てることはできますか？ 

バーチャルレポートスイートはデータを収集しないため、Advertising Analytics アカウントをバーチャルレポートスイートに直接マッピングすることはできません。 ただし、Advertising Analytics アカウントは、データを表示するバーチャルレポートスイートの親レポートスイートにマッピングできます。 AMO ID （またはその分類）に基づいてセグメントロジックに「or」条件を含めない限り、検索エンジンの指標（クリック/コスト/インプレッション）が仮想レポートスイートに表示されない場合があります。 例：「AMO ID が存在するすべてのヒット」を追加すると、セグメント内の検索エンジンの指標が含まれます。

+++

+++ Advertising Analytics指標は、*マーケティングチャネル* レポートでレポートできますか？ 

いいえ、マーケティングチャネルレポートには含まれていません。

+++

+++ 検索データは、いつAnalyticsに取り込まれますか？ 

検索データは、Analytics データセンターのタイムゾーンの午前6時頃（06:00）に検索エンジンから取得されます。 この時点で AMO データが収集され、レポートスイートに挿入されます。 さらに AMO データは Analytics へのデータ挿入の一環としてレポートスイートのタイムゾーンに変換されます。

+++

+++ クリック *の前に* キャプチャできるものは何ですか？ クリックしなくても、インプレッション、コスト、平均順位などを取り込めますか？

AMO IDは、インプレッション数、コスト、クリック数、平均順位、平均品質スコアなどの検索エンジン指標を取得します。 クリックはないがインプレッションがある場合、インプレッション/位置/品質スコアデータは引き続きAnalyticsに送信されます。 通常、クリックがない場合はコストもかかりません。

+++

+++ このデータはどのレベルでキャプチャされますか？ *訪問者ですか？ ヒット？* 

検索エンジンの指標はヒットレベルでキャプチャされ、AMO ID （およびその分類）に接続されます。 これは概要レベルのデータであり、訪問/訪問者には接続されていません。 そのため、検索エンジン指標は、ヒットレベルのスコープで、AMO ID （またはその分類）に基づくセグメントでのみ使用できます。

AMO IDは、そのページのヒットのランディングページ（訪問/訪問者に接続する）にもキャプチャされ、ダウンストリームに残り、他のAnalytics指標のクレジットを取得します（有効期限が切れるか、新しいAMO IDによって上書きされるまで）。 他のeVarと同様に、データセットに完全に組み込まれています。

+++

+++ google.comまたは&#x200B;*国のバージョン* （google.co.uk、google.it、google.fr、google.deなど）のみをキャプチャしますか？ 

Ad Platform分類は、「Google Adwords」および「Bing Ads」という値をキャプチャします。 一般的なベストプラクティスとして、キャンペーンの名前の一部に国コードを含めます。 これにより、フィルタリングしたりセグメント化したりできます（例：すべてのキャンペーンがcountrycode_ で始まる場合、「UK_」で始まるキャンペーン（AMO ID）のセグメントを作成すると、UK のデータのみが提供されます）。

+++

+++ 「AMO コスト」という指標は、検索エンジンによって報告される、各キーワード/広告に対して支払われたコストです。 「純費用」か「総費用」か？ 

「AMO コスト」とは、検索エンジンに支払われたコストのみです。 代理店や検索最適化/管理プラットフォームの料金は含まれていません。

+++

+++ *ディスプレイ*&#x200B;や&#x200B;*ソーシャル*&#x200B;など、他の広告チャネルを含める計画はありますか？ 

いいえ、現在、ロードマップのその他のチャネルに関する計画はありません。

+++


## 自動トラッキングと手動トラッキング {#section_7437C4698A6D482EB7ED94A948390119}

+++ Advertising アカウントを設定すると、*自動トラッキング*&#x200B;が意図しない結果につながる可能性があることを示しています。 どのような結果が起こる可能性がありますか？ 

自動モードでは、トラッキングテンプレート/宛先URLの末尾にURL パラメーターを正しい形式で追加しようとします。 ただし、追加されたURL パラメーターが最終的なランディングページに正しく保持されるようにするのは、ユーザーの責任です。 自動モードはランディング URLにキーワードを挿入でき、Web サーバーは特殊文字を含むキーワードをサポートしない場合があります。

+++

+++ 最初に手動または自動トラッキングを設定した場合、後で他のトラッキングモードに切り替えることはできますか？ どのような影響があるでしょうか。 

はい、トラッキングモードを切り替えることはできますが、切り替える前に古いトラッキングロジックを削除する必要があります。 これにより、スイッチが切り替えられた日にトラッキングがダウンタイムになる可能性があります（特に手動から自動に移動する場合）。 そのため、絶対に必要でない限り切り替えないことをお勧めします。

* 手動から自動への切り替え：トラッキングテンプレートの手動の追加を削除し、Advertising Analytics UIの切り替えスイッチを手動から自動に切り替えて、設定を保存します。 システムが自動トラッキングコードを入力するのに数時間かかる場合があります。

* 自動から手動への切り替え：Advertising Analytics設定UIで手動から自動への切り替えを更新し、手動トラッキングコードをできるだけ早くデプロイします。 手動トラッキングコードのデプロイ中に、検索エンジンのトラッキングテンプレートに自動トラッキングコードが表示された場合は、それらを削除します。

+++
