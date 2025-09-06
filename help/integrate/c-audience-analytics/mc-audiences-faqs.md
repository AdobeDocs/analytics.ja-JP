---
description: Audience Analytics を実装するときによくある質問への回答です。
solution: Experience Cloud
title: Audience Analytics に関するよくある質問（FAQ）
feature: Audience Analytics
exl-id: 86e7967c-030c-44d6-8294-e7e6d41f6fc3
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '1090'
ht-degree: 31%

---

# よくある質問

Audience Analytics を実装するときによくある質問への回答です。

## 法的事項についてよくある質問（FAQ） {#legal}

+++ Analytics データに個人を特定できる情報（PII）があるかどうかを確認するにはどうすればよいですか？ もしそうなら私はどうすればいいの？

prop またはeVarにメールやアドレスなどがある場合は、収集時にデータをハッシュ化することを検討します。 国が IP アドレスを PII と見なす場合は、[IP の不明化を有効にする ](/help/admin/tools/exclude-ip.md) を選択します。 Analytics 管理者に問い合わせて、収集しているものを確認します。 法務部門に問い合わせて、PII と見なされる項目を確認します。

+++

+++ レポートスイートがオンサイトパーソナライゼーションを行っているか、オフサイト/オンサイトターゲティングを行っているかを知るには、どうすればよいですか？

これらは、Adobe Analytics データをAdobe Audience Managerに送信する場合には適用されません。 次の点を確認してください。

* Analytics で共有されるセグメントを MCA ディメンションと共有して、Experience Cloudに戻すことはできますか？

* これらの目的で使用するビジネスインテリジェンス（BI）システムに（データフィードなどを介して）エクスポートしますか。

+++

## Adobe Audience Manager固有の FAQ {#aam-specific}

+++ Audience Managerで Analytics の宛先を作成するにはどうすればよいですか？

[Adobe Audience Managerでの Analytics の宛先の設定」を参照してください ](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/destinations/experience-cloud-destinations/create-analytics-destination.html?lang=ja)

+++

+++ Analytics の宛先を作成して保存した後、選択したレポートスイートにデータが表示されるまで、どのくらい時間がかかりますか？

レポートスイートに新しいデータが入力されるまでに数時間かかることがあります。

+++

+++ 新しい Analytics の宛先を作成しましたが、使用可能なセグメントの「宛先マッピング」セクションに表示されません。 その宛先はどこに行ったのですか、それとも見つけるにはどうすればよいですか？

**[!UICONTROL セグメントマッピング]** で「**[!UICONTROL 現在および将来のすべてのセグメントを自動的にマッピング]**」オプションを選択すると、Analytics の宛先がセグメントの「宛先マッピング」セクションに表示されなくなります。 これを防ぐには、自動オプションの代わりに「**[!UICONTROL Manually map segments]**」を選択します。

+++

Adobe Audience Managerの Analytics に関する情報をすべて入手できますか？

いいえ。Audience Manager オーディエンスの有効化中または有効化後、およびセグメント認定中／認定後にサイトを訪問するユーザーに関連するデータのみ提供されます。

+++

+++ セグメントごとの合計アドレス可能なオーディエンスを提供できますか？

いいえ。セグメント認定中または認定後にサイトを訪れた、そのセグメントの訪問者数が提供されます。

+++

+++ 従来の cookie の宛先から Analytics への移行との違いは何ですか？

セグメントはに対して選定され、同じヒットでリアルタイムに返されます。 わかりやすい名前が自動的に表示されます。

+++

+++ レポートスイートに個人データが含まれているものと含まれていないレポートスイートがある場合はどうすればよいですか？&lt;

ヒント：2 つの宛先を作成します。個人データレポートスイートを 1 つの宛先に追加し、個人データ以外のレポートスイートを別の宛先に追加します。

+++

## Analytics 固有のよくある質問（FAQ） {#aa-specific}

+++ この統合は、Analytics でディメンションまたはセグメントとして表示されますか。

ディメンション（オーディエンス ID およびオーディエンス名）として表示されます。

+++

+++Analytics でこれらのディメンションを使用できる場所を教えてください。

あらゆる場所で、Analytics で収集された他のディメンションと同様に扱われます。

+++

+++ データが Analytics で通過しないのはなぜですか。

データソースと出力先の間で、Adobe Audience Managerのプライバシーコントロールが競合している可能性があります。

+++

+++ すべてのセグメントの送信を選択したのに、Analytics で一部のセグメントが欠落しているのはなぜですか。&lt;

* 宛先とセグメントのデータソース内で、Adobe Audience Manager データ書き出しのコントロールが競合し、特定のセグメントが送信されない可能性があります。

* セグメントでサードパーティのデータ特性を使用している場合、それらのセグメントは個人データを含む宛先（一連のレポートスイート）と共有できません。

+++

+++ Analytics レポートに「オーディエンス制限に達しました」と表示されるのはなぜですか？ （メモ：また、Data Warehouseでは「Audience ID = -1」および「`::max_audiences_exceeded::`」としても表示されます）

デフォルトでは、Adobe Audience ManagerのAudience Analytics統合により、訪問者が該当するすべてのセグメントがヒットごとに Analytics に送信されます。 訪問者が 1 回のヒットで 150 を超えるAdobe Audience Manager セグメントに属している場合、最近選定された **150 個のセグメント** が Analytics に送信され、残りのリストは切り捨てられます。 セグメントリストが切り捨てられたことを示す追加のフラグが Analytics に送信され、オーディエンス名ディメンションに「オーディエンスの制限に達しました」と表示され、オーディエンス ID ディメンションに「-1」が表示されます。

特定のヒットで訪問者が 150 を超えるセグメントに認定されることはあまりありませんが、まれに起こる可能性があります。レポートに「オーディエンスの制限に達しました」が表示される場合は、2 つの選択肢があります。

* オプション 1：統合を標準の状態で引き続き機能させ、特定の訪問者に対して最近選定された 150 個のセグメントを送信する。

* オプション 2:Adobe Audience Managerで、統合に関するビジネスに最も重要な 150 のセグメントを選択します。 Adobe Audience Managerは、これら 150 個のセグメントに対してのみ訪問者をチェックします。 この手法の欠点は、すべての訪問者に対してこの 150 セグメントしか受け取れないことです。一方、1 の手法の場合、統合にはヒットごとの特性があるので、セグメントを無制限に送信できます。

+++

+++ この統合では、追加のサーバーコールに対して Analytics に請求されますか？

いいえ。Adobe Audience Manager Audiences は、サーバーサイドで Analytics ヒットに組み込まれます。 これは、Analytics（プライマリまたはセカンダリ）への追加のサーバーコールとなりません。

+++

## サーバーサイド転送（SSF）のよくある質問（FAQ） {#SSF}

+++ 従来の SSF が実装されている場合は、Analytics Admin に移動して、レポートスイート SSF を有効にする必要がありますか？

はい。Adobe Audience Managerの宛先の設定では、SSF がオンになっているレポートスイートのみが表示されます。

+++

+++ Analytics Admin で SSF 用の特定のレポートスイートを有効にできないのはなぜですか？

Experience Cloud 組織にマップされているスイートのみを有効にできます。

このトピックに関するその他の FAQ については、[サーバーサイド転送 FAQ](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-faq.md)を参照してください。

+++

## 一般事項についてのよくある質問（FAQ） {#section_E55410BBFB624AAFB87ADCF7F036DDA3}

+++ Audience Managerと Analytics でセグメント訪問者カウントが異なるのはなぜですか？

[ 訪問者数の違い ](/help/integrate/c-audience-analytics/visitor-count-reconciliation.md) を参照してください。

+++

+++ Adobe Audience Managerの「オーディエンス」と Analytics の「セグメント」の違いは何ですか？

[Analytics とAudience Managerのセグメントについて ](/help/integrate/c-audience-analytics/aam-analytics-segments.md) を参照してください。 Adobe Audience Manager オーディエンスは、Analytics で使用される「ディメンション」コンポーネントとして送信および共有されます。 これらは、セグメントビルダーのセグメントとしては表示されません（例：セグメントの作成に使用できるディメンション）。

+++

+++ Adobe Audience Managerから統合された顧客属性と顧客データの違いは何ですか？

顧客属性は時間に基づくものではありません。遡及的に適用され、先に進みます。 Adobe Audience Manager統合データは、時間ベースで将来に向けての提供のみです。 さらに、顧客属性はExperience Cloudの訪問者 ID のルックアップテーブルであるのに対して、Adobe Audience Manager統合は、訪問者の各ヒットにステッチされるデータです。

+++

+++ 古いベータ版やコンサルティングプラグイン cookie の宛先など、この問題に対する従来のアプローチはどうですか？

新しい統合を実装して古い宛先を削除することを推奨します。

+++
