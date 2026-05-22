---
description: Audience Analytics を実装するときによくある質問への回答です。
solution: Analytics
title: Audience Analytics に関するよくある質問（FAQ）
feature: Audience Analytics
exl-id: 86e7967c-030c-44d6-8294-e7e6d41f6fc3
TQID: 'https://experienceleague.adobe.com/5dYdPb8Erenemm1Q5Cn79fH-MChshnxJtdD7O33MaHk'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
subfeature_v2:
  - id: a97e0d8c-238a-47ee-8d81-16bd45309bed
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 1120
ht-degree: 14%

---

# よくある質問

Audience Analytics を実装するときによくある質問への回答です。

## 法的事項についてよくある質問（FAQ） {#legal}

+++ Analytics データに個人を特定できる情報（PII）があるかどうかを確認するにはどうすればよいですか？ もし「はい」の場合、どうすればよいでしょうか？

propまたはeVarにメール/アドレスなどが含まれている場合は、収集中にデータをハッシュ化することを検討してください。 お住まいの国がIP アドレスをPIIと見なしている場合、[IP難読化を有効にする](/help/admin/tools/exclude-ip.md)。 Analytics管理者に問い合わせて、収集しているデータを確認します。 法務部門に問い合わせて、PIIとは何かを確認する。

+++

+++ レポートスイートがオンサイトのパーソナライゼーションを行うか、オフサイト/オンサイトのターゲティングを行うかを確認するにはどうすればよいですか？

これらは、Adobe Analytics データをAdobe Audience Managerに送信する場合は適用されません。 次の質問に自問自答：

* MCA ディメンションを含むAnalytics共有セグメントをCX Enterpriseに共有しますか？

* これらの目的のために使用されるBusiness Intelligence（BI）システムに（データフィードなどを介して）書き出すのですか？

+++

## Adobe Audience Managerに関するFAQ {#aam-specific}

+++ Audience ManagerでAnalyticsの宛先を作成するにはどうすればよいですか？

「[Adobe Audience ManagerでのAnalyticsの宛先の設定](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/destinations/experience-cloud-destinations/create-analytics-destination.html?lang=ja)」を参照してください。

+++

+++ Analytics宛先を作成して保存した後、選択したレポートスイートにデータが表示されるまでにどのくらいの時間がかかりますか？

レポートスイートに新しいデータを入力するには、数時間かかる場合があります。

+++

+++ 新しいAnalytics宛先を作成しましたが、利用可能なセグメントの「宛先マッピング」セクションに表示されません。 その目的地はどこに行ったのか、どうすれば見つけることができるのか？

**[!UICONTROL セグメントマッピング]**&#x200B;で「**[!UICONTROL 現在および将来のすべてのセグメントを自動的にマッピング]**」オプションを選択すると、Analytics宛先がセグメントの「宛先マッピング」セクションから消えます。 これを防ぐには、自動オプションの代わりに&#x200B;**[!UICONTROL 手動でセグメントをマッピング]**&#x200B;を選択します。

+++

+++ Adobe AnalyticsのAdobe Audience Managerから得られるすべての情報を確認します？

いいえ。Audience Manager Audiencesの有効化中または有効化後、およびセグメントの適格化中/後にサイトにアクセスした人に関連するデータのみが対象です。

+++

+++ セグメントごとの合計アドレス可能なオーディエンスを表示できるか？

そうではありません。 セグメントの選定の際または後にサイトにアクセスした、そのセグメントの訪問者の数が表示されます。

+++

+++ 従来のCookieの宛先とAnalyticsの違いは何ですか？

セグメントは、同じヒットでリアルタイムに適格および返されます。 わかりやすい名前が自動的に表示されます。

+++

+++ レポートスイートの一部に個人データがあり、一部に個人データがない場合はどうなりますか？&lt;

ヒント：2つの宛先を作成 – 個人データレポートスイートを1つの宛先に追加し、非個人データレポートスイートを他の宛先に追加します。

+++

## Adobe Analyticsに関するFAQ {#aa-specific}

+++ この統合は、Analyticsのディメンションまたはセグメントとして表示されますか？

ディメンション：オーディエンス IDとオーディエンス名。

+++

+++Analyticsでこれらのディメンションはどこで使用できますか？

どこでも。Analyticsで収集された他のディメンションと同じように扱われます。

+++

+++ Analyticsでデータが表示されないのはなぜですか？

データソースと宛先の間でAdobe Audience Managerのプライバシー制御が競合している可能性があります。

+++

+++ すべてのセグメントを送信することを選択したにもかかわらず、一部のセグメントがAnalyticsに表示されないのはなぜですか？&lt;

* 宛先とセグメントのデータソースにおけるAdobe Audience Manager データ書き出し制御が競合している可能性があり、特定のセグメントが送信されない可能性があります。

* セグメントでサードパーティのデータ特性を使用している場合、それらのセグメントは個人データを含む宛先（一連のレポートスイート）と共有できません。

+++

+++ Analytics レポートに「Audience limit reached」が表示されるのはなぜですか？ （注：これは、Data WarehouseではAudience ID = -1および`::max_audiences_exceeded::`としても表されます）

デフォルトでは、Adobe Audience Manager用のAudience Analytics統合は、訪問者が適格なすべてのセグメントを、ヒットごとにAnalyticsに送信します。 1回のヒットで訪問者が150個を超えるAdobe Audience Manager セグメントに属している場合、**150個の最も最近に選定されたセグメント**&#x200B;がAnalyticsに送信され、残りのリストは切り捨てられます。 セグメントリストが切り捨てられたことを示す追加のフラグが Analytics に送信され、オーディエンス名ディメンションに「オーディエンスの制限に達しました」と表示され、オーディエンス ID ディメンションに「-1」が表示されます。

特定のヒットで訪問者が 150 を超えるセグメントに認定されることはあまりありませんが、まれに起こる可能性があります。 レポートに「オーディエンスの制限に達しました」が表示される場合は、2 つの選択肢があります。

* オプション 1：統合がすぐに利用できる状態で引き続き機能し、特定の訪問者に対して最も最近選定された150個のセグメントを送信します。

* 選択肢2:Adobe Audience Managerで、自社にとって最も重要な150のセグメントを選択して統合します。 その後、Adobe Audience Managerは150のセグメントに対してのみ訪問者をチェックします。 このアプローチの欠点は、すべての訪問者で150個のセグメントのみを受け取ることです。 一方、オプション 1 アプローチでは、統合のヒットごとの性質により、セグメントを無制限に配信できます。

+++

+++ この統合の場合、追加のサーバーコールはAnalyticsに請求されますか？

いいえ。 Adobe Audience Manager Audiencesは、Analytics ヒットのサーバーサイドに組み込まれます。 Analytics （プライマリまたはセカンダリ）への追加のサーバーコールは発生しません。

+++

## サーバーサイド転送（SSF）のよくある質問（FAQ） {#SSF}

+++ 従来のSSFが実装されている場合、Analytics管理者にも移動してレポートスイート SSFを有効にする必要がありますか？

はい。 Adobe Audience Managerの宛先設定では、SSFが有効になっているレポートスイートのみが表示されます。

+++

+++ Analytics AdminでSSFの特定のレポートスイートを有効にできない理由

CX Enterprise組織にマッピングされたスイートのみが有効にできます。

このトピックに関するその他の FAQ については、[サーバーサイド転送 FAQ](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-faq.md)を参照してください。

+++

## 一般事項についてのよくある質問（FAQ） {#section_E55410BBFB624AAFB87ADCF7F036DDA3}

+++ Audience ManagerとAnalyticsでセグメント訪問者数が異なるのはなぜですか？

[訪問者数の違い](/help/integrate/c-audience-analytics/visitor-count-reconciliation.md)を参照してください。

+++

+++ Adobe Audience Managerの「オーディエンス」とAnalyticsの「セグメント」の違いは何ですか？

AnalyticsとAudience Managerのセグメントについて[を参照してください](/help/integrate/c-audience-analytics/aam-analytics-segments.md)。 Adobe Audience Manager オーディエンスは、Analyticsで使用する「ディメンション」コンポーネントとして送信され、共有されます。 例えば、セグメントビルダーではセグメントとして表示されませんが、セグメントを構築できるディメンションとして表示されます。

+++

+++ Adobe Audience Managerに統合された顧客属性と顧客データの違いは何ですか？

顧客属性は、時間ベースではありません。過去にさかのぼって適用され、先に進みます。 Adobe Audience Managerとの統合データは、時間ベースで前進専用です。 さらに、顧客属性はCX Enterprise訪問者IDのルックアップテーブルですが、Adobe Audience Manager統合は訪問者の各ヒットにデータをつなぎ合わせています。

+++

+++ 古いベータ版やコンサルティングプラグインのcookieの宛先など、この問題に対する従来のアプローチはどうでしょうか？

新しい統合を実装し、古い宛先を削除することをお勧めします。

+++
