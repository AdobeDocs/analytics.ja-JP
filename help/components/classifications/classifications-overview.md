---
title: 分類の概要
description: ディメンション項目のグループ化をカスタマイズします。
feature: Classifications
exl-id: 0d2c77ea-610f-48e0-b6a2-6e91794783b1
source-git-commit: 1e209d4313c3d9d67f15a0c3a0939ceeb7a1ed31
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 38%

---

# 分類の概要

分類とは、Analytics 変数データをカテゴリーにまとめ、レポートを生成する際に様々な方法でデータを表示する手法です。変数値とその値に関連するメタデータとの間の関係を確立します。分類は、[&#x200B; トラッキングコード &#x200B;](/help/components/dimensions/tracking-code.md)、[props](/help/components/dimensions/prop.md)、[eVar](/help/components/dimensions/evar.md) など、ほとんどのカスタムディメンションで使用できます。

* **分類セット** は、データを分類する主なコンポーネントです。 [&#x200B; 分類セット &#x200B;](/help/components/classifications/sets/overview.md) を使用すると、単一のシンプルなインターフェイスで分類を作成および管理できます。

* **従来の分類** では、データを分類するための従来の分類方法について説明しています。 これらのメソッドは、非推奨（廃止予定）となり、2026 年 8 月 31 日（PT）以降はアクセスできなくなります。

   * [分類ルール](/help/components/classifications/crb/classification-rule-builder.md)：特定のディメンション項目を分類ディメンション項目に割り当てるルールを作成します。このデータの分類方法は、ディメンションで新しい一意の値が頻繁に見つかる場合や、手動での分類が頻繁で負担になる場合に最適です。
   * [分類インポーター](/help/components/classifications/importer/c-working-with-saint.md)：各行のディメンション項目を含むテンプレートスプレッドシートを書き出します。列は、ディメンションの各分類を表します。このデータ分類方法は、すべてのディメンション項目が既知で、頻繁に更新する必要がない場合に最適です。

1 つのディメンションに複数の分類ディメンションを含めることができます。例えば、製品名、カラー、サイズ、説明、SKU などの追加の製品属性を使用して [!UICONTROL &#x200B; 製品 ID] を分類できます。 これらの各属性は、同じ親ディメンションに属する個別の分類ディメンションになります。 これらの属性でレポートを拡張すると、より深く複雑なレポートの機会が提供されます。 ディメンションに分類データが含まれると、分類ディメンション項目のみを含むレポートで分類ディメンションを使用できます。 分類値を含まない親分析コード項目は、[&#x200B; 未指定 &#x200B;](/help/technotes/unspecified.md) にグループ化されます
