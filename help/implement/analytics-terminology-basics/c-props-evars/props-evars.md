---
description: カスタムトラフィック変数（prop（s.prop）またはプロパティ変数とも呼ばれます）は、各変数が Analytics に送信された回数をカウントするカウンターです。
keywords: Analytics Implementation;Traffic prop;prop;conversion;evar;s.prop;custom conversion insight;traffic variable
solution: Analytics
title: prop と eVar の概要
topic: Developer and implementation
uuid: 522cab2b-1ef8-4f10-b216-c82b21431487
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# prop と eVar の概要

カスタムトラフィック変数（prop（s.prop）またはプロパティ変数とも呼ばれます）は、各変数が Analytics に送信された回数をカウントするカウンターです。

割り当てる変数のタイプや場所を判断する際は、prop と eVar の機能性の違いを理解していることが重要です。これらの違いを理解していれば、最適の変数のタイプを判断できます。詳しくは、「[Prop と eVar の比較](/help/implement/analytics-terminology-basics/c-props-evars/props-vs-evars.md)」を参照してください。

また、prop は、カスタムデータを特定のトラフィック関連イベントに相互に関連付けることができます。これらの変数は、Web サイトの各ページの [!DNL Analytics] コードに埋め込まれます。[!UICONTROL  は、]s.prop[!DNL Analytics] 変数を使用して、組織、産業、およびビジネス目標に特有のカスタムレポートの作成を可能にします。

例えば、自動車メーカーでは、「ページ」レポートを完成させるために「最も人気のある車種」を把握したい場合があります。これをおこなうには、トラフィックプロパティの 1 つを割り当てて、車種を表します。次に、適切なページで車種を渡すコードを導入します。

> [!NOTE][!DNL Analytics] では、最大 75 個の [!UICONTROL s.prop] 変数をサポートします。

prop は、パスレポートやクロス集計レポートで使用されます。例えば、[!UICONTROL プロパティ]変数を使用して、コンテンツタイプ、サブセクションまたはテンプレート名を示すことができます。作成される[!UICONTROL カスタムトラフィック]レポートには、最も頻繁に閲覧されるコンテンツタイプ、サブセクションまたはテンプレートが示されます。

Web サイトから取り込む情報に応じて、カスタムトラフィック変数を使用して回答できるビジネスの質問は無数にあります。次の一覧に、よく使用される目標をいくつか示します。

* Web サイト内のユーザーナビゲーションの把握
* サイト内検索の利用状況の把握
* ナビゲーションまたはカテゴリ別のトラフィックのセグメント化
* 人口統計に基づく訪問者行動のセグメント化

eVar（または [!UICONTROL カスタムコンバージョンインサイト]変数）は、特定の属性やアクションがサイトの成功イベントにどの程度貢献しているかを確認するために使用されます。例えば、メディアサイトでは、内部プロモーションがどの程度訪問者の登録を促すかを確認するために eVar を使用できます。訪問者が内部プロモーションをクリックしたときに、eVar を使用して、そのプロモーションの一意の識別子を保存することができます。同じ訪問者が登録を完了してカスタムの成功イベントが発生すると、元の一意の識別子は、登録イベントのクレジットを受け取ります。

コンバージョンサイトでは、ログインしていない訪問者と比較して、ログインした訪問者がどのように購入を完了するかを追跡するのに eVar を使用できます。訪問者がログインしたとき、eVar は「logged in」に設定されます。その訪問者がチェックアウトページに到達したとき、チェックアウトイベントが「logged in」値に関連付けられます。訪問者が購入後に「ご購入ありがとうございました」ページに到達したとき、製品と購入金額が「logged in」値に関連付けられます。作成される[!UICONTROL カスタム eVar] レポートには、「ログインした」訪問者と「ログインしていない」訪問者のチェックアウト数および注文数の合計が示されます。

その他の情報については、Analytics ヘルプとリファレンスの[トラフィック変数](https://marketing.adobe.com/resources/help/en_US/reference/traffic_var.html)を参照してください。

Digital Tag Management でプロパティを作成する方法については、「[Web プロパティの作成](/help/implement/c-implement-with-dtm/t-create-web-property.md)」を参照してください。
