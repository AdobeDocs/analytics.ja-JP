---
description: Audience Analytics を実装するときによくある質問への回答です。
solution: Experience Cloud
title: Audience Analytics に関するよくある質問（FAQ）
feature: Audience Analytics
exl-id: 86e7967c-030c-44d6-8294-e7e6d41f6fc3
source-git-commit: c947de8eaa4e4dc3a0c10989ef6ae450cebc1f3e
workflow-type: tm+mt
source-wordcount: '1091'
ht-degree: 31%

---

# よくある質問

Audience Analytics を実装するときによくある質問への回答です。

## 法的事項についてよくある質問（FAQ） {#legal}

+++ Analytics データに個人識別情報 (PII) が含まれているかどうかを確認するには、どうすればよいですか。 そうなったらどうすればいいの？

prop またはeVarに電子メールやアドレスなどがある場合は、収集中にデータをハッシュすることを検討してください。 お客様の国で IP アドレスが PII（個人情報）と見なされる場合、 [IP の不明化を有効にする](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/exclude-ip.html?lang=ja). 何を収集しているかを確認するには、Analytics 管理者に問い合わせてください。 PII と見なされるものを確認するには、法務部門に問い合わせてください。

+++

+++ レポートスイートでオンサイトのパーソナライゼーションまたはオフサイト/オンサイトのターゲティングがおこなわれているかどうかを確認するには、どうすればよいですか。

これらは、Adobe Audience ManagerへのAdobe Analyticsデータの送信には適用されません。 自問自答：

* MCA ディメンションで Analytics 共有セグメントを共有して、Experience Cloudに戻りますか？

* これらの目的で使用するビジネスインテリジェンス（BI）システムに（データフィードなどを介して）エクスポートしますか。

+++

## Adobe Audience Manager固有の FAQ {#aam-specific}

+++ Analytics の宛先を作成する方法を教えてください。Audience Manager

詳しくは、 [Adobe Audience Managerでの Analytics の宛先の設定](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/destinations/experience-cloud-destinations/create-analytics-destination.html?lang=ja)&quot;.

+++

+++ Analytics の宛先を作成して保存した後、選択したレポートスイートにデータが表示されるまで、どれくらいかかりますか。

レポートスイートに新しいデータが入力されるまでに数時間かかることがあります。

+++

+++ 新しい Analytics の宛先を作成しましたが、使用可能なセグメントの「 Destination Mappings 」セクションに表示されません。 その目的地はどこに行ったのですか？また、どうすれば見つけられますか？

Analytics の宛先は、 **[!UICONTROL 現在および将来のすべてのセグメントを自動的にマッピング]** オプション **[!UICONTROL Segment Mappings]**. これを防ぐには、自動オプションの代わりに「**[!UICONTROL Manually map segments]**」を選択します。

+++

Analytics で、Adobe Audience Managerからすべての情報が提供されますか。

いいえ。Audience Manager オーディエンスの有効化中または有効化後、およびセグメント認定中／認定後にサイトを訪問するユーザーに関連するデータのみ提供されます。

+++

+++ これにより、セグメントごとにアドレス可能なオーディエンスの合計が提供されますか？

いいえ。セグメント認定中または認定後にサイトを訪れた、そのセグメントの訪問者数が提供されます。

+++

+++ Analytics の宛先との従来の Cookie の違いは何ですか？

セグメントは、同じヒットでリアルタイムに認定されて返されます。 わかりやすい名前が自動的に表示されます。

+++

+++ レポートスイートに個人データが含まれているものと含まれていないものがある場合はどうなりますか？&lt;

ヒント：2 つの宛先を作成します。個人データレポートスイートを 1 つの宛先に追加し、個人データ以外のレポートスイートを別の宛先に追加します。

+++

## Analytics 固有のよくある質問（FAQ） {#aa-specific}

+++ この統合は、Analytics でディメンションまたはセグメントとして表示されますか。

ディメンションとして：オーディエンス ID およびオーディエンス名。

+++

+++これらのディメンションは Analytics のどこで使用できますか？

どこでも、Analytics で収集される他のディメンションと同様に扱われます。

+++

+++ Analytics でデータが受信されないのはなぜですか？

データソースと宛先の間に競合するAdobe Audience Managerのプライバシー制御がある可能性があります。

+++

+++ すべてのセグメントを送信するように選択しましたが、一部のセグメントが Analytics で欠落しているのはなぜですか。&lt;

* 宛先とセグメントのデータソースのAdobe Audience Managerデータ書き出しコントロールが競合して、特定のセグメントが送信されない可能性があります。

* セグメントでサードパーティのデータ特性を使用している場合、それらのセグメントは個人データを含む宛先（一連のレポートスイート）と共有できません。

+++

+++ Analytics レポートに「オーディエンスの上限に達しました」と表示されるのはなぜですか。 ( 注意：これは、オーディエンス ID = -1 および「:」としても表されます。:max_audiences_exceeded::&quot; (Data Warehouse)

デフォルトでは、Adobe Audience ManagerのAudience Analytics統合は、訪問者が認定するすべてのセグメントをヒットごとに Analytics に送信します。 1 回のヒットで訪問者が 150 を超えるAdobe Audience Managerセグメントに属している場合、 **最近認定された 150 個のセグメント** 残りのリストは切り捨てられる間、が Analytics に送信されます。 セグメントリストが切り捨てられたことを示す追加のフラグが Analytics に送信され、オーディエンス名ディメンションに「オーディエンスの制限に達しました」と表示され、オーディエンス ID ディメンションに「-1」が表示されます。

特定のヒットで訪問者が 150 を超えるセグメントに認定されることはあまりありませんが、まれに起こる可能性があります。レポートに「オーディエンスの制限に達しました」が表示される場合は、2 つの選択肢があります。

* オプション 1：統合を標準の状態で引き続き実行し、特定の訪問者に対して最近絞り込まれた 150 個のセグメントを送信します。

* オプション 2:Adobe Audience Managerで、統合に関してビジネスにとって最も重要な 150 個のセグメントを選択します。 次に、Adobe Audience Managerは、これら 150 個のセグメントに対してのみ訪問者をチェックします。 この手法の欠点は、すべての訪問者に対してこの 150 セグメントしか受け取れないことです。一方、1 の手法の場合、統合にはヒットごとの特性があるので、セグメントを無制限に送信できます。

+++

+++ この統合に関して、Analytics には追加のサーバーコールが請求されますか？

いいえ。Adobe Audience Manager Audiences は、Analytics のヒットサーバーサイドに組み込まれます。 これは、Analytics（プライマリまたはセカンダリ）への追加のサーバーコールとなりません。

+++

## サーバーサイド転送（SSF）のよくある質問（FAQ） {#SSF}

+++ 従来の SSF を実装している場合は、Analytics 管理者に移動して、レポートスイート SSF を有効にする必要がありますか。

はい。Adobe Audience Managerの宛先設定では、SSF が有効になっているレポートスイートのみが表示されます。

+++

+++ Analytics 管理で特定のレポートスイートを SSF に対して有効にできないのはなぜですか。

Experience Cloud 組織にマップされているスイートのみを有効にできます。

このトピックに関するその他の FAQ については、[サーバーサイド転送 FAQ](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-faq.md)を参照してください。

+++

## 一般事項についてのよくある質問（FAQ） {#section_E55410BBFB624AAFB87ADCF7F036DDA3}

+++ セグメント訪問者数が Analytics と Analytics で異なるのはなぜですか？

詳しくは、 [訪問者数の違い](/help/integrate/c-audience-analytics/visitor-count-reconciliation.md).

+++

+++ Adobe Audience Managerの「オーディエンス」と Analytics の「セグメント」の違いは何ですか。

詳しくは、 [Analytics とAudience Managerのセグメントについて](/help/integrate/c-audience-analytics/aam-analytics-segments.md). Adobe Audience Managerオーディエンスは、Analytics で使用する「ディメンション」コンポーネントとして送信および共有されます。 セグメントビルダーなどにはセグメントとしては表示されませんが、セグメントを作成する際に使用できるディメンションとして表示されます。

+++

+++ 顧客属性と、Adobe Audience Managerから統合された顧客データの違いは何ですか。

顧客属性は時間ベースではありません。後で適用され、将来的に適用されます。 Adobe Audience Managerの統合データは、時間ベースで将来のみ利用できます。 また、Experience Cloud属性は顧客 ID のルックアップテーブルです。Adobe Audience Manager統合は、訪問者の各ヒットに関連付けられたデータです。

+++

+++ この問題に対する従来のアプローチ（古いベータ版やコンサルティングプラグインの Cookie の宛先など）はどうなりますか。

新しい統合を実装して古い宛先を削除することを推奨します。

+++
