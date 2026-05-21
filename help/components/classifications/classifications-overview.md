---
title: 分類の概要
description: ディメンション項目のグループ化をカスタマイズします。
feature: Classifications
exl-id: 0d2c77ea-610f-48e0-b6a2-6e91794783b1
TQID: https://experienceleague.adobe.com/raB90u-JEBgDroQPLC1eCSmxs4V-J7Av8Snr6oeKwvk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 309
ht-degree: 84%

---

# 分類の概要

分類とは、Analytics 変数データをカテゴリーにまとめ、レポートを生成する際に様々な方法でデータを表示する手法です。 変数値とその値に関連するメタデータとの間の関係を確立します。 分類は、[トラッキングコード](/help/components/dimensions/tracking-code.md)、[prop](/help/components/dimensions/prop.md)、[eVar](/help/components/dimensions/evar.md) など、ほとんどのカスタムディメンションで使用できます。

* **分類セット**&#x200B;は、データを分類する主なコンポーネントです。 [分類セット](/help/components/classifications/sets/overview.md)を使用すると、シンプル化された 1 つのインターフェイスで、分類を作成および管理できます。

* **従来の分類**&#x200B;では、データを分類する従来の分類方法について文書化します。 これらのメソッドは近日中に廃止され、アクセスできなくなります。

   * [分類ルール](/help/components/classifications/crb/classification-rule-builder.md)：特定のディメンション項目を分類ディメンション項目に割り当てるルールを作成します。 このデータ分類方法は、ディメンションで新しい一意の値が頻繁に検出される場合や、手動による分類が頻繁に発生し負荷がかかる場合に最適です。 この機能は、2027年2月28日以降に非推奨（廃止予定）となります。

   * [分類インポーター](/help/components/classifications/importer/c-working-with-saint.md)：各行のディメンション項目を含むテンプレートスプレッドシートを書き出します。 列は、ディメンションの各分類を表します。 このデータ分類方法は、すべてのディメンション項目が既知で、頻繁に更新する必要がない場合に最適です。 この機能は、2026年8月31日（PT）以降に非推奨（廃止予定）となります。 廃止により、標準のFTPを使用して分類を読み込むことができなくなります。

1 つのディメンションに複数の分類ディメンションを含めることができます。 例えば、製品名、カラー、サイズ、説明、SKU などの追加の製品属性を使用して[!UICONTROL 製品 ID] を分類できます。 これらの各属性は、同じ親ディメンションに属する個別の分類ディメンションになります。 これらの属性を使用してレポートを拡張すると、より深く複雑なレポートの機会が提供されます。 ディメンションに分類データが含まれると、分類ディメンション項目のみを含むレポートで分類ディメンションを使用できるようになります。 分類値が含まれていない親ディメンション項目は、[未指定](/help/technotes/unspecified.md)にグループ化されます
