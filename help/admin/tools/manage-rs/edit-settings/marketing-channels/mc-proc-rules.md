---
title: マーケティングチャネルの処理ルール
description: ルールを使用して、ヒットがどのマーケティングチャネルに属するかを決定します。
feature: Marketing Channels
exl-id: 825f70a5-cce3-4b1c-bb42-828388348216
role: Admin
source-git-commit: e934de3938f013067d6bbd6b516b0444b0c9f782
workflow-type: tm+mt
source-wordcount: '819'
ht-degree: 3%

---

# マーケティングチャネルの処理ルール

_このページは、ヒットにマーケティングチャネルを割り当てる処理ルールを参照します。 データの収集方法を調整できる機能については、[ 処理ルール ](../general/processing-rules/pr-overview.md) を参照してください。_

マーケティングチャネルの処理ルールを使用すると、[ マーケティングチャネル ](/help/components/dimensions/marketing-channel.md) および [ マーケティングチャネルの詳細 ](/help/components/dimensions/marketing-detail.md) ディメンションの値を決定するロジックを作成できます。 [ マーケティングチャネルマネージャー ](c-channels.md) を使用して使用するマーケティングチャネルを決定し、処理ルールを使用して各チャネルの設定方法を決定します。

![ マーケティングチャネルバケット ](assets/buckets_2.png)

**[!UICONTROL Analytics]**/**[!UICONTROL 管理者]**/**[!UICONTROL レポートスイート]**/**[!UICONTROL 設定編集]**/**[!UICONTROL マーケティングチャネル]**/**[!UICONTROL マーケティングチャネルの処理ルール]**

[ 自動設定 ](/help/components/c-marketing-channels/c-getting-started-mchannel.md) が実行されると、設定時に生成された各チャネルのルールが作成されます。

![ デフォルトのルール ](assets/marketing_channel_rules.png)

複数のルールを使用して、1 つのマーケティングチャネルを定義できます。 1 つのチャネルに複数のルールを使用すると、ルール条件に応じてチャネルの詳細を異なる方法で設定する場合に役立ちます。 複数の条件を使用して 1 つのルールを定義することもできます。

## ルールの定義

各ルールには、条件と割り当てが含まれます。

* **[!UICONTROL 次のいずれかまたはすべてが当てはまる場合]**:1 つのルールに複数の条件を追加した場合、チャネルおよび関連する値を設定するために、すべての条件を満たす必要があるか、いずれかの条件を満たす必要があるかを決定できます。
* **ルール条件**：満たす必要がある 1 つ以上のルール条件を指定します。 通常は、マーケティングチャネルに適合するためにヒットが一致する必要があるディメンションを指定します。
* **[!UICONTROL 次の操作を実行します]**：ルールの条件が一致したら、[ マーケティングチャネル ](/help/components/dimensions/marketing-channel.md) （[!UICONTROL  チャネルを次として識別 ]）および [ マーケティングチャネルの詳細 ](/help/components/dimensions/marketing-detail.md) （[!UICONTROL  チャネルの値を設定 ]）を設定します。

## ルール条件

ルール条件を設定する際には、次のオプションを使用できます。

>[!NOTE]
>
>すべてのテキストフィールドは、**大文字と小文字を区別しない** として評価されます。 例えば、クエリ文字列パラメーター `cmp` が `abc123` であるルール条件を使用する場合、クエリ文字列パラメーターと値の両方で大文字と小文字を任意に組み合わせて使用できます。

**Adobeが検出した条件** テキストを入力するオプションやフィールドを含めないでください。

| Adobeが検出した条件 | 説明 |
|---|---|
| **[!UICONTROL 有料検索検知ルールに一致]** | ヒットは、認識された検索エンジンから発生し、一致した [ 有料検索検出ルール ](../general/paid-search-detection/paid-search-detection.md)。 |
| **[!UICONTROL 自然検索検知ルールに一致]** | ヒットが、認識された検索エンジンから発生し、有料検索検出ルールに一致しませんでした。 |
| **[!UICONTROL リファラーが内部 URL フィルターと一致]** | ヒットには、「内部 URL フィルター [ に一致する ](/help/components/dimensions/referrer.md) リファラー [ が含まれてい ](../general/internal-url-filter-admin.md) す。 |
| **[!UICONTROL リファラーが内部 URL フィルターに一致しません]** | ヒットに、内部 URL フィルターに一致しないリファラーが含まれていました。 |
| **[!UICONTROL 訪問の最初のヒット]** | そのヒットは訪問の最初のものだった。 |
| **[!UICONTROL リファラーはソーシャルネットワークです]** | [ リファラータイプ ](/help/components/dimensions/referrer-type.md) は「ソーシャルネットワーク」です。 |
| **[!UICONTROL リファラーはソーシャルネットワークではありません]** | リファラータイプは「ソーシャルネットワーク」ではありません。 |
| **[!UICONTROL リファラーは対話型 AI]** | リファラータイプは「対話型 AI」です。 |
| **[!UICONTROL リファラーは対話型 AI ではありません]** | リファラータイプは「対話型 AI」ではありません。 |

**ヒット属性** を使用すると、ディメンション、一致する演算子、検索する値を指定できます。

| ヒット属性条件 | 説明 |
|---|---|
| **[!UICONTROL ページ]** | [ページ](/help/components/dimensions/page.md)ディメンション。 |
| **[!UICONTROL ページドメイン]** | URL のドメイン。 例：`products.example.com`。 |
| **[!UICONTROL ページドメインとパス]** | URL のドメインとパス。 例：`products.example.com/mens/pants/overview.html`。 |
| **[!UICONTROL ページルートドメイン]** | URL のルートドメイン。 例：`example.co.uk`。 |
| **[!UICONTROL ページ URL]** | 完全なページ URL。 |
| **[!UICONTROL クエリ文字列パラメーター]** | ページ URL の個々のクエリ文字列パラメーター。 ルール条件ごとに 1 つのクエリ文字列パラメーターを使用します。 ルールに複数のクエリ文字列パラメーターを含める場合は、複数のルール条件を使用します。 |
| **[!UICONTROL リファラー]** | 「[リファラー](/help/components/dimensions/referrer.md)」ディメンション。 |
| **[!UICONTROL 参照ドメイン]** | [ 参照ドメイン ](/help/components/dimensions/referring-domain.md) ディメンション。 |
| **[!UICONTROL 参照ドメインとパス]** | 参照ドメインとリファラーの URL パスの連結。 例えば、`www.example.com/products/id/12345` や `ad.example.com/foo` です。 |
| **[!UICONTROL 参照パラメーター]** | リファラー内のクエリ文字列パラメーター。 |
| **[!UICONTROL 参照ルートドメイン]** | 参照ルートドメイン。 |
| **[!UICONTROL 検索エンジン]** | 「[ 検索エンジン ](/help/components/dimensions/search-engine.md)」ディメンション。 |
| **[!UICONTROL 検索キーワード]** | 「[ 検索キーワード ](/help/components/dimensions/search-keyword.md)」ディメンション。 |
| **[!UICONTROL 検索エンジン +検索キーワード]** | 検索エンジンと検索キーワードの連結。 |
| **[!UICONTROL AMO ID]** | Adobe AdvertisingとAdvertising Analyticsの統合で使用されるプライマリトラッキングコード。 これらの統合のいずれかが有効になっている場合は、トラッキングコードのプレフィックスを使用して、Advertising固有のチャネルを識別できます。 「AL」で始まる値は検索およびソーシャル用です。 「AC」で始まる値は表示用です。 AMO ID がマーケティングチャネルで使用される場合、クリック/コスト/インプレッション指標は正しいチャネルに関連付けることができます。 |
| **[!UICONTROL AMO EF ID]** | Adobe Advertisingで使用されるセカンダリトラッキングコード。 データをAdvertisingに送り返すためのキーとして機能します。 これを使用すると、2 つの異なるマーケティングチャネルとして、表示クリックスルーと表示ビュースルーを識別できます。 これを行うには、「AMO EF ID」のマーケティングチャネルロジックが、ディスプレイクリックスルーの場合は `:d` で終わり、ディスプレイビュースルーの場合は「AMO EF ID」が `:i` で終わるように設定します。 表示を 2 つのチャネルに分割しない場合は、代わりに AMO ID ディメンションを使用します。 |

**コンバージョン変数** を使用すると、カスタム eVar、一致する演算子、検索する値を指定できます。

| コンバージョン変数の条件 | 説明 |
|---|---|
| **eVar 1-250** | 関連付けられた [eVar](/help/components/dimensions/evar.md) ディメンション。 |
