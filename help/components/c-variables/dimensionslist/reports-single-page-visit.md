---
description: Ad Hoc Analysis の直帰数指標とは異なります。直帰数レポートは、Web サイトへの訪問者が入口として使用し、他のページを表示する手順をおこなわずにそのまま出口に使用したページを示します。
seo-description: Ad Hoc Analysis の直帰数指標とは異なります。直帰数レポートは、Web サイトへの訪問者が入口として使用し、他のページを表示する手順をおこなわずにそのまま出口に使用したページを示します。
seo-title: 直帰数
solution: Analytics
title: 直帰数
topic: レポート
uuid: 5ca52be8- c7f5-464a-8a06-55e8271760b4
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 直帰数

Ad Hoc Analysis の直帰数指標とは異なります。直帰数レポートは、Web サイトへの訪問者が入口として使用し、他のページを表示する手順をおこなわずにそのまま出口に使用したページを示します。

このレポートが最も一般的に使用されるのは[!UICONTROL ページ]レポートのコンテキストですが、[!UICONTROL パス]が有効になっているすべてのトラフィック変数でも表示できます。このレポートを使用すると、訪問者に対してサイトの他のページヘの誘導率が最も低い入口ページを識別したり、単一のページから成る訪問の数を判断できます。この情報により、コンテンツを最適化して該当ページでの離脱を減らすことができます。

## レポートのプロパティ {#section_2D30F939FE0648EF983DD7C1BAB1181B}

* [!UICONTROL ページ]レポートで[!UICONTROL 単一アクセス]を指標として使用することにより、同一のレポートを取得できます。

* 直帰数は、単一のイメージリクエストではなく 1 つのユニーク値を含む訪問とみなされます。

   * "[ページレポート](../../../components/c-variables/dimensionslist/reports-pages.md#concept_0219136EA25745B58434D0C7E751D7D5)のコンテキストでは、1 つだけの個別ページが訪問内で呼び出されます。
   * [サイトセクションレポート](../../../components/c-variables/dimensionslist/reports-site-sections.md#concept_39E550D7A9E34C9580E81F5F9E12BDDD)のコンテキストでは、単一の一意のサイトセクションが訪問内で呼び出されます。
   * [トラフィック変数](/help/admin/admin/c-traffic-variables/traffic-var.md)のコンテキストでは、単一の固有値が呼び出されると、訪問によってこのレポートが入力されます。

* レポートのコンテキストにある変数には単一のユニーク値が含まれている限り、多数のイメージリクエストで直帰数が構成されることも可能です。2 番目のユニーク値が入力されると、その訪問は直帰数とはみなされなくなります。
* これは一種のパスレポートとみなされます。デフォルトでは、[!UICONTROL ページ]変数ではパスが有効になっています。ただし、いずれのトラフィック変数にもこの機能があります。トラフィック変数でパスが有効かどうかは、契約によって異なります。詳しくは、アカウントマネージャーにお問い合わせください。
* このレポートでは、検索フィルターを使用して特定の行項目を見つけることができます。
* This report can be viewed in both [trended](/help/components/c-variables/dimensionslist/reports-types.md) and [ranked](/help/components/c-variables/dimensionslist/reports-types.md) formats.

* このレポートで分類は使用できません。
* このレポート内で使用可能な唯一の指標は[!UICONTROL 訪問回数]です。

