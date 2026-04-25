---
title: ハッシュの競合
description: ハッシュの競合とは何かと、どのようにレポートで示されるかについて説明します。
feature: Implementation Basics
exl-id: 693d5c03-4afa-4890-be4f-7dc58a1df553
role: Admin, Developer
source-git-commit: e6dd38fe34d7e0ab69bdf1c68716427905caa356
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 5%

---

# ハッシュの競合

Adobe Analyticsのディメンションは、文字列値を収集します。 これらの文字列は数百文字の場合もあれば、短い場合もあります。 パフォーマンスを向上させるために、これらの文字列値は、レポート時処理で直接使用されません。 代わりに、値ごとにハッシュが計算され、均一なサイズの識別子が生成されます。 ほとんどのフィールドでは、値はハッシュする前に小文字に変換され、一意の値の合計数が減少します。 すべてのレポートは、これらのハッシュ化された値で実行されるため、パフォーマンスが大幅に向上します。

Adobe Analyticsでは、各変数に対して個別のハッシュテーブルを保持し、各テーブルは毎月再構築されます。 これらのテーブルのいずれかで、2つの異なるソース値が同じハッシュを生成することがあります。これは&#x200B;*ハッシュ コリジョン*&#x200B;と呼ばれます。

ハッシュの衝突は、次のようにレポートに表示されます。

* レポートを時系列で表示し、予期しないスパイクを確認した場合、その変数の複数の一意の値が同じハッシュを使用している可能性があります。
* セグメントを使用して予期しない値を確認した場合、予期しないディメンション項目で、セグメントに一致する別のディメンション項目と同じハッシュが使用される可能性があります。

## ハッシュ衝突の確率

Adobe Analyticsでは、ほとんどのディメンションに32 ビットハッシュが使用されます。つまり、2<sup>32</sup>個のハッシュの組み合わせが可能です（約43億）。 一意の値の数に基づいて、ハッシュ衝突が発生する近似確率は次のとおりです。 これらのオッズは、1か月間の単一のディメンションにもとづいています。

| 一意の値 | オッズ |
| --- | --- |
| 1,000 | 0.01% |
| 10,000 | 1% |
| 50,000 | 26% |
| 100,000 | 71% |

[誕生日パラドックス ](https://en.wikipedia.org/wiki/Birthday_problem)と同様に、一意の値の数が増えるにつれて、ハッシュ衝突の可能性が大幅に増加します。 100万の一意の値では、そのディメンションに対して少なくとも100回のハッシュ衝突が発生している可能性があります。

## ハッシュ衝突の緩和

ハッシュ衝突を完全に排除することはできませんが、レポートへの影響を軽減することはできます。 ほとんどのハッシュ衝突は、2つの珍しい値で発生し、レポートに意味のある影響を与えません。 ハッシュが共通および非共通の値と衝突しても、結果は無視できます。 しかし、2つの一般的な値がハッシュ衝突を経験するまれなケースでは、その効果を明確に確認することができます。 Adobeでは、レポートでの効果を減らすために、次のことをお勧めします。

* **日付範囲を変更**: ハッシュテーブルは毎月変更されます。 日付範囲を別の月にまたがるように変更すると、各値に衝突しない異なるハッシュが設定される場合があります。 通常、特定のレポートから目に見える異常値を除去する最も高速な方法です。
* **一意の値の数を減らします**：実装を調整するか、[処理ルール ](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)を使用して、ディメンションが収集する一意の値の数を減らすことができます。 例えば、ディメンションでURLを収集した場合、クエリ文字列またはプロトコルを削除できます。
* **使用[Data Warehouse](/help/export/data-warehouse/data-warehouse.md)または[ データフィード](/help/export/analytics-data-feed/data-feed-overview.md)**：これらのツールはハッシュテーブルに依存しません。
* **[Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=ja)**&#x200B;に移動：Customer Journey Analyticsにはハッシュレイヤーがなく、[ ディメンションに基数制限がありません](https://experienceleague.adobe.com/docs/analytics-platform/using/components/dimensions/high-cardinality.html)。 ハッシュの衝突または[[!UICONTROL 低トラフィック ]](/help/technotes/low-traffic.md)が頻繁にレポートに影響を与える場合は、この製品への移行を検討してください。

>[!MORELIKETHIS]
>
>* Adobe Analytics](/help/technotes/low-traffic.md)の[[!UICONTROL Low-Traffic]値
>* [処理ルールの概要](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)

<!-- https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=OmniArch&title=Uniques -->
