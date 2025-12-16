---
title: 分類セットの概要
description: 分類セットを使用して分類データを管理する方法を説明します。 分類セットと従来の分類との違いを理解します。
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
feature: Classifications
source-git-commit: 0f80bb314c8e041a98af26734d56ab364c23a49b
workflow-type: tm+mt
source-wordcount: '950'
ht-degree: 9%

---

# 分類セットの概要

分類セットは、分類とルールを管理するための単一のインターフェイスを提供します。このワークフローは、[ レポートスイート設定 ](/help/admin/tools/manage-rs/report-suites-admin.md) での分類の作成と [ 分類インポーター ](/help/components/classifications/sets/manage/set-manager.md) を組み合わせたものです。 その結果、分類データを作成および管理するための直感的なインターフェイスが 1 つになりました。


## 分類セットと従来の分類

分類セットと従来の分類の主な違いは、分類セットが、従来の分類が 3 つのインターフェイスに依存する 1 つのインターフェイスですべての機能を組み合わせることである。

### 従来の分類

![ レガシー分類 ](/help/components/classifications/sets/assets/classifications-legacy.svg)

従来の分類では、分類 ![ スキーマ ](/help/assets/icons2/Schema.svg) （トラフィック、コンバージョン、マーケティングチャネルなど）にはそれぞれ独自のディメンション（キー ![](/help/assets/icons2/Key.svg)）があります。 これらの分類は、[ レポートスイート設定 ](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-classifications.md) の一部として定義します。

![ 分類ルールビルダー ](/help/assets/icons/BidRule.svg) インターフェイスの一部として、ルールセットで個別にルール [BidRule](/help/components/classifications/crb/classification-rule-builder.md) を定義します。 このインターフェイスでは、ルールセットを 1 つ以上のレポートスイートに関連付けます。

[ 分類インポーター ](/help/components/classifications/importer/c-working-with-saint.md) を使用して、テンプレート ![DocumentFragment](/help/assets/icons/DocumentFragment.svg) をダウンロードしたり、レポートスイートのキー（データセット）の組み合わせから ![UploadToCloud](/help/assets/icons/UploadToCloud.svg) 分類を読み込んだり、![ ダウンロード ](/help/assets/icons/Download.svg) 分類を書き出したりできます。



### 分類セット

![ 分類セット ](./assets/classifications-sets.svg)

分類セットは、従来の分類インターフェイスをすべて 1 つに組み合わせます。 各分類セットは、次の項目を定義します。

* 分類する 1 つ以上の購読（レポートスイート ![ データ ](/help/assets/icons2/Data.svg) とディメンション ![ キー ](/help/assets/icons2/Key.svg) （キー）の組み合わせ）。 製品 SKU に基づいて製品を分類する場合は、該当する製品 SKU ディメンションを持つすべてのレポートスイートを定義できます。 また、従来の分類インターフェイスのように、レポートスイートをまたいで分類をレプリケートする必要はありません。
* キーの分類 ![ スキーマ ](/help/assets/icons2/Schema.svg) （スキーマ）のリスト。 例えば、製品の分類の場合、カテゴリ、色、サイズ、性別などを指定できます。 分類を定義したら、テンプレート ![DocumentFragment](/help/assets/icons/DocumentFragment.svg) のダウンロード、分類データ ![UploadToCloud](/help/assets/icons/UploadToCloud.svg) のアップロード、分類データ ![ ダウンロード ](/help/assets/icons/Download.svg) のダウンロードなどが可能です。
* 分類をサポートする 1 つ以上のルール ![BidRule](/help/assets/icons/BidRule.svg)。


Adobe Analytics インターフェイスの **[!UICONTROL コンポーネント]** メニューから **[!UICONTROL 分類セット]** にアクセスするには、製品管理者であるか、権限項目 [!UICONTROL  レポートスイートツール ]/[!UICONTROL  分類 ] を含む製品プロファイルに属している必要があります。 従来の分類管理インターフェイスは、**[!UICONTROL 管理]** メニューから使用できます。

分類セットは、次の 3 つの機能領域で構成されます。

* [**[!UICONTROL  分類セット ]**](manage/set-manager.md)：分類セットを作成、編集および削除する。
* [**[!UICONTROL  ジョブ ]**](job-manager.md)：分類セットジョブのステータスを表示します。
* [**[!UICONTROL  統合 ]**](consolidations/manage.md)：複数の分類セットを 1 つの分類セットに組み合わせます。


## ワークフロー

通常、分類セットのワークフローには次の手順が含まれます。

1. 分類セットを作成するレポートスイートとディメンションの組み合わせを検討します。 例えば、詳細を含む製品を分類するレポートスイートに対して作成した製品分類セットを定義します。 例えば、カテゴリや色などの詳細です。
1. 製品を識別する 1 つ以上のレポートスイートとキーディメンションの組み合わせのサブスクリプションを使用して、[ 分類セットを作成 ](/help/components/classifications/sets/manage/create.md) します。 例：

   | レポートスイート | 主要なディメンション |
   |---|---|
   | レポートスイート 1 | 製品 ID |
   | レポートスイート 2 | 製品 SKU |

1. 識別した分類を分類セットスキーマに [ 追加 ](/help/components/classifications/sets/manage/schema.md#add) します。 例：

   | 分類名 | ID 名 |
   |---|---|
   | カテゴリ | category |
   | Color | color |

1. 分類データを含むファイルを手動で作成します。 [ テンプレートを使用 ](/help/components/classifications/sets/manage/schema.md#template) して、[ サポートされているファイル形式 ](data-files.md#classification-set-file-formats) とファイルの列を確実に使用します。 次に、データをテンプレートファイルに追加します。

   または、テンプレートに準拠した列を使用して、[ サポートされているファイル形式 ](data-files.md#classification-set-file-formats) で製品カタログから直接データを書き出すこともできます。 例えば、次のような CSV ファイルです。

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

   分類データファイルでは、**[!UICONTROL を使用して各レポートスイートの主要なディメンション（例：]** 製品 ID **[!UICONTROL および]** 製品 SKU`Key`）を参照します。 また、**[!UICONTROL 分類名]** を使用して、各分類を参照できます（例：`Category` または `Color`）。

1. [ アップロード ](/help/components/classifications/sets/manage/schema.md#upload) 分類データを含むファイルを分類セットスキーマに追加します。

1. 受信データと過去のデータを自動的に分類する [ ルール ](manage/rules.md) を設定します。

1. [ 自動化 ](/help/components/classifications/sets/manage/schema.md#automate) クラウドの場所を使用して、分類データに反映させる、製品カタログの更新プロセス。

1. [ ダウンロード ](/help/components/classifications/sets/manage/schema.md#download) 分類データを使用して、コンテンツを検証します。

1. [ ジョブ履歴を検査 ](/help/components/classifications/sets/job-manager.md) して、分類でのアクション（アップロード、ダウンロード、テンプレートなど）の結果を確認します。
1. 従来の分類機能から移行した結果、類似した分類セットが複数ある場合は、これらの分類セットを [ 統合 ](consolidations/manage.md) します。



## 機能強化

分類セットでリリースされたバックエンドアーキテクチャには、いくつかの改善点が含まれています。

* 処理時間を短縮しました（72 時間から 24 時間に短縮）。
* 分類を管理するための再設計されたユーザーインターフェイス。
* 分類データ用の [Adobe Analytics ソースコネクタ ](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/classifications) を介してAdobe Experience Platformで分類データを使用するオプション。

分類セットでリリースされたバックエンドアーキテクチャには、次のようないくつかの変更も含まれています。

* ブラウザーまたは自動読み込みを使用する場合、**[!UICONTROL 競合時に上書き]** は常に有効になっています。
* ブラウザーまたは自動読み込みを使用する場合、読み込み直後に書き出すオプションはサポートされなくなりました。書き出しは、別途開始する必要があります。
* Analytics 2.0 `GetDimensions` API エンドポイントで、数値識別子ではなく、分類の文字列識別子を返すようになりました。 数値識別子は引き続き使用できますが、可能な限り新しい文字列識別子を使用することをお勧めします。 数値識別子は、`?expansion=hidden` クエリ文字列パラメーターを使用して取得できます。

>[!IMPORTANT]
>
>分類セットのパフォーマンスは、主に、データを含む一意のキー値の数に依存します。一意の値を多数含む変数がある場合は注意が必要です。 特に、複数のレポートスイートやディメンションのこのような変数を 1 つの分類セットに組み合わせる場合。

## 制限事項

* 分類セットは、まだルールをサポートしていません。 [ 従来のルールビルダー ](/help/components/classifications/crb/classification-rule-builder.md) 機能が使用できなくなる前に、ルール機能が分類セットインターフェイスに追加されます。
* 従来の分類ルールおよび設定を分類セットに移行する必要はありません。 従来の分類機能が使用できなくなる前に、移行ユーティリティが分類セットインターフェイスに追加されます。
