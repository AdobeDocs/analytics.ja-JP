---
title: 分類の概要
description: ディメンション項目のグループ化をカスタマイズします。
feature: Classifications
exl-id: 0d2c77ea-610f-48e0-b6a2-6e91794783b1
source-git-commit: e4cfebf6a6932f66ac78ea2f7cea747ce558cf96
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 71%

---

# 分類の概要

分類とは、Analytics 変数データをカテゴリーにまとめ、レポートを生成する際に様々な方法でデータを表示する手法です。変数値とその値に関連するメタデータとの間の関係を確立します。分類は、[トラッキングコード](/help/components/dimensions/tracking-code.md)、[prop](/help/components/dimensions/prop.md)、[eVar](/help/components/dimensions/evar.md) など、ほとんどのカスタムディメンションで使用できます。

* **分類セット**&#x200B;は、データを分類する主なコンポーネントです。[分類セット](/help/components/classifications/sets/overview.md)を使用すると、シンプル化された 1 つのインターフェイスで、分類を作成および管理できます。

* **従来の分類**&#x200B;では、データを分類する従来の分類方法について文書化します。これらのメソッドは近い将来に非推奨となり、アクセスできなくなります。

   * [分類ルール](/help/components/classifications/crb/classification-rule-builder.md)：特定のディメンション項目を分類ディメンション項目に割り当てるルールを作成します。このデータの分類方法は、ディメンションで新しい一意の値が頻繁に見つかる場合や、手動での分類が頻繁で負担になる場合に最適です。 この機能は、2027 年 2 月 28 日（PT）以降に廃止されます。

   * [分類インポーター](/help/components/classifications/importer/c-working-with-saint.md)：各行のディメンション項目を含むテンプレートスプレッドシートを書き出します。列は、ディメンションの各分類を表します。このデータの分類方法は、すべてのディメンション項目が既知で、頻繁な更新を必要としない場合に最適です。 この機能は、2026 年 8 月 31 日（PT）以降に廃止されます。 廃止すると、標準の FTP を使用して分類をインポートできなくなります。

1 つのディメンションに複数の分類ディメンションを含めることができます。例えば、製品名、カラー、サイズ、説明、SKU などの追加の製品属性を使用して[!UICONTROL 製品 ID] を分類できます。これらの各属性は、同じ親ディメンションに属する個別の分類ディメンションになります。これらの属性を使用してレポートを拡張すると、より深く複雑なレポートの機会が提供されます。ディメンションに分類データが含まれると、分類ディメンション項目のみを含むレポートで分類ディメンションを使用できるようになります。分類値が含まれていない親ディメンション項目は、[未指定](/help/technotes/unspecified.md)にグループ化されます
