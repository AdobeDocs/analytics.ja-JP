---
title: 分類セットの概要
description: 分類セットを使用して分類データを管理する方法について説明します。分類セットと従来の分類との違いを理解します。
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
feature: Classifications
source-git-commit: e1ccd006336f10b8f843d59cfdcd220064524349
workflow-type: tm+mt
source-wordcount: '895'
ht-degree: 100%

---

# 分類セットの概要

分類セットは、分類とルールを管理するための単一のインターフェイスを提供します。このワークフローでは、[レポートスイート設定](/help/admin/tools/manage-rs/report-suites-admin.md)での分類の作成と[分類インポーター](/help/components/classifications/sets/manage-sets.md)を組み合わせます。その結果、分類データを作成および管理する単一の直感的なインターフェイスが実現します。


## 分類セットと従来の分類

分類セットと従来の分類の主な違いは、分類セットではすべての機能を 1 つのインターフェイスに統合するのに対し、従来の分類では 3 つのインターフェイスに依存していることです。

### 従来の分類

![従来の分類](/help/components/classifications/sets/assets/classifications-legacy.svg)

従来の分類では、分類 ![スキーマ](/help/assets/icons2/Schema.svg)（トラフィック、コンバージョン、マーケティングチャネルなど）ごとに独自のディメンション（キー ![キー](/help/assets/icons2/Key.svg)）があります。これらの分類は、[レポートスイート設定](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-classifications.md)の一部として定義します。

[分類ルールビルダー](/help/components/classifications/crb/classification-rule-builder.md)インターフェイスの一部として、ルールセットでルール ![BidRule](/help/assets/icons/BidRule.svg) を個別に定義します。このインターフェイスで、ルールセットを 1 つ以上のレポートスイートに関連付けます。

[分類インポーター](/help/components/classifications/importer/c-working-with-saint.md)を使用して、テンプレート ![DocumentFragment](/help/assets/icons/DocumentFragment.svg) のダウンロード、レポートスイートとキー（データセット）の組み合わせへの分類の読み込み ![UploadToCloud](/help/assets/icons/UploadToCloud.svg) 、レポートスイートとキー（データセット）の組み合わせからの分類の書き出し ![ダウンロード](/help/assets/icons/Download.svg) を行います。



### 分類セット

![分類セット](./assets/classifications-sets.svg)

分類セットは、すべての従来の分類インターフェイスを 1 つに組み合わせます。各分類セットは、次の項目を定義します。

* 分類するレポートスイート ![データ](/help/assets/icons2/Data.svg) とディメンション ![キー](/help/assets/icons2/Key.svg)（キー）の組み合わせである 1 つ以上のサブスクリプション。製品 SKU に基づいて製品を分類する場合は、該当する製品 SKU ディメンションを使用してすべてのレポートスイートを定義できます。また、従来の分類インターフェイスのように、レポートスイートをまたいで分類をレプリケートする必要はありません。
* キーの分類 ![スキーマ](/help/assets/icons2/Schema.svg)（スキーマ）のリスト。例えば、製品の分類では、カテゴリ、カラー、サイズ、性別などを指定できます。分類を定義したら、テンプレート ![DocumentFragment](/help/assets/icons/DocumentFragment.svg) のダウンロード、分類データのアップロード ![UploadToCloud](/help/assets/icons/UploadToCloud.svg) 、分類データのダウンロード ![ダウンロード](/help/assets/icons/Download.svg) などを行うことができます。
* 分類をサポートする 1 つ以上のルール ![BidRule](/help/assets/icons/BidRule.svg)。


Adobe Analytics インターフェイスの&#x200B;**[!UICONTROL コンポーネント]**&#x200B;メニューから&#x200B;**[!UICONTROL 分類セット]**&#x200B;にアクセスするには、製品管理者であるか、権限項目の[!UICONTROL レポートスイートツール]／[!UICONTROL 分類]を含む製品プロファイルに属している必要があります。従来の分類管理インターフェイスは、**[!UICONTROL 管理]**&#x200B;メニューから使用できます。

分類セットは、次の 3 つの機能領域で構成されます。

* [**[!UICONTROL 分類セット]**](manage-sets.md)：分類セットを作成、編集および削除します。
* [**[!UICONTROL ジョブ]**](job-manager.md)：分類セットジョブのステータスを表示します。
* [**[!UICONTROL 統合]**](consolidations/manage.md)：複数の分類セットを 1 つの分類セットに組み合わせます。


## ワークフロー

分類セットのワークフローには通常、次の手順が含まれます。

1. 分類セットを作成するレポートスイートとディメンションの組み合わせを考慮します。例えば、製品をより詳細に分類するレポートスイートに対して作成する製品分類セットを定義します。例えば、カテゴリやカラーなどの詳細です。
1. 製品を識別する 1 つ以上のレポートスイートとキーディメンションの組み合わせのサブスクリプションを含む[分類セットを作成](/help/components/classifications/sets/create-set.md)します。例：

   | レポートスイート | キーディメンション |
   |---|---|
   | レポートスイート 1 | 製品 ID |
   | レポートスイート 2 | 製品 SKU |

1. 分類セットスキーマに識別した[分類を追加](/help/components/classifications/sets/manage/schema.md#add)します。 例：

   | 分類名 | ID 名 |
   |---|---|
   | カテゴリ | カテゴリ |
   | カラー | カラー |

1. 分類データを含むファイルを手動で作成します。[テンプレートを使用](/help/components/classifications/sets/manage/schema.md#template)して、[サポートされているファイル形式](data-files.md#classification-set-file-formats)と列を使用していることを確認します。 次に、テンプレートファイルにデータを追加します。

   または、テンプレートに準拠した列を含む[サポートされているファイル形式](data-files.md#classification-set-file-formats)で、製品カタログからデータを直接書き出すこともできます。例えば、次のような CSV ファイルです。

   ```
   Key,Category,Color
   Adobe Nike Tech Fleece Full-Zip Hoodie - Men's,Men,Black
   Adobe Nike Tech Fleece Full-Zip Hoodie - Women's,Women,Black
   Men's North Face Adobe Jacket,Men,Black
   Nike Air Hybrid 2 Golf Bag,Equipment,Blue
   STITCH&reg; Ultimate Garment Bag,Equipment,Brown
   Adobe Analytics Training Tee - Navy,Men,Navy
   AirPods Pro 2,Electronics,White
   Adobe Analytics Training Tee - Green,Men,Green
   Women's North Face Adobe Jacket,Women,Blue
   Adobe Analytics Training Tee - Grey,Men,Gray
   Adobe Analytics One Million Views - Grey,Equipment,Grey
   Adobe and MGM Tee - White,Women,White
   Adobe and MGM Tee - Charcoal,Women,Charcoal
   ```

   分類データファイルでは、`Key` を使用して各レポートスイートのキーディメンション（例：**[!UICONTROL 製品 ID]** および&#x200B;**[!UICONTROL 製品 SKU]**）を参照します。また、**[!UICONTROL 分類名]**（例：`Category` または `Color`）を使用して各分類を参照します。

1. 分類データを含むファイルを分類セットスキーマに[アップロード](/help/components/classifications/sets/manage/schema.md#upload)します。

1. 受信データと過去のデータを自動的に分類する[ルール](manage/rules.md)を設定します。

1. クラウドの場所を使用して、分類データに反映される製品カタログの更新プロセスを[自動化](/help/components/classifications/sets/manage/schema.md#automate)します。

1. 分類データを[ダウンロード](/help/components/classifications/sets/manage/schema.md#download)して、コンテンツを検証します。

1. [ジョブ履歴を調査](/help/components/classifications/sets/job-manager.md)して、分類に対するアクション（アップロード、ダウンロード、テンプレートなど）の結果を確認します。
1. 従来の分類機能からの移行の結果として、複数の類似した分類セットがある場合は、これらの分類セットを[統合](consolidations/manage.md)します。



## 機能強化

分類セットでリリースされたバックエンドアーキテクチャには、次のいくつかの改善点が含まれています。

* 処理時間の短縮（72 時間から 24 時間へ）。
* 分類を管理するための再設計されたユーザーインターフェイス。
* [分類データ用の Adobe Analytics ソースコネクタ](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/connectors/adobe-applications/classifications)を介して、Adobe Experience Platform で分類データを使用するオプション。

分類セットでリリースされたバックエンドアーキテクチャには、次のいくつかの変更点も含まれています。

* ブラウザーまたは自動読み込みを使用する場合、「**[!UICONTROL 競合時に上書き]**」は常に有効になっています。
* ブラウザーまたは自動読み込みを使用する場合、読み込み直後に書き出すオプションはサポートされなくなりました。書き出しは、別途開始する必要があります。
* Analytics 2.0 API `GetDimensions` エンドポイントは、数値識別子ではなく、分類の文字列識別子を返すようになりました。数値識別子は引き続き使用できますが、可能な限り新しい文字列識別子を使用することをお勧めします。数値識別子は、`?expansion=hidden` クエリ文字列パラメーターを使用して取得できます。

>[!IMPORTANT]
>
>分類セットのパフォーマンスは、主に、データを含む一意のキー値の数に依存します。一意の値が多数含まれる変数がある場合は注意してください。特に、複数のレポートスイートやディメンションのこのような変数を 1 つの分類セットに組み合わせる場合は注意してください。
