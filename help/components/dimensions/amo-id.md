---
title: AMO ID
description: Adobe Advertising統合で使用される Adobe Media Optimizer ID。
feature: Dimensions
source-git-commit: 408d8db0d1e3c8301a066fe54d611ec7b8e3418a
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 3%

---

# AMO ID

**[!UICONTROL AMO ID]** は、Adobe Advertising統合で使用される連結された識別子のコレクションです。 このディメンションに保存される値は、Analytics レポートで使用するために、人間が読み取りやすい個別の分類ディメンションに自動的に整理されます。 [Analytics for Advertising](https://experienceleague.adobe.com/ja/docs/advertising/integrations/analytics/overview) 統合を有効にすると、ディメンションが自動的に作成されます。

## このディメンションへのデータ入力

このディメンションは、次の複数の方法で値を収集します。

* クリックスルートラフィックの場合、データは、通常、広告ドリブン型トラフィックがサイトに入るページにある `s_kwcid` ページ URL[&#x200B; の &#x200B;](page-url.md) クエリ文字列パラメーターから収集されます。
* クリックスルートラフィックは、URL にトラッキングコードが含まれていないが、Adobe Advertising JavaScriptによって過去 2 分以内にクリックが検出された場合にもキャプチャできます。
* サポートされているビュースルートラフィックの場合、Adobe Advertisingは、追加の ID （`SDID`）を使用してバックエンドの値を補完します。

## ディメンション項目

Dimension項目には、AMO ID （`s_kwcid` 値とも呼ばれます）が含まれます。 正確な形式は、トラフィックがDSPから発生したものか、検索、ソーシャル、Commerceから発生したものかによって異なります。 AMO ID は EF ID ほど詳細ではなく、主に Analytics でのAdobe Advertising指標の分類と取り込みに使用されます。

### DSP

```text
AC!{ad key}!{placement key}
```

* **`AC`**：表示チャネルを示します。
* **`ad key`**:Adobe Advertisingで生成された広告の英数字 ID。
* **`placement key`**:Adobe Advertisingで生成されるプレースメント用の英数字 ID。

値の例：

```text
AC!iIMvXqlOa6Nia2lDvtgw!GrVv6o2oV2qQLjQiXLC7
```

### 広告の検索、ソーシャル、Commerce

検索、ソーシャル、Commerce AMO ID は、`AL` で始まり、次に広告主ユーザー ID、広告ネットワークアカウント ID、ネットワーク固有の識別子が続きます。 共有広告ネットワークアカウント ID には、次のものが含まれます。

* **`3`**:Google広告
* **`10`**:MicrosoftAdvertising
* **`45`**:Meta
* **`86`**: Yahoo! ネットワークを表示
* **`87`**: Naver
* **`88`**: Baidu
* **`90`**: Yandex
* **`94`**: Yahoo! 日本広告
* **`105`**:Yahoo ネイティブ（非推奨）
* **`106`**:Pinterest（非推奨）

#### Google 広告

Google Ads では、2 つの関連する形式を使用します。 新しいアカウントには、キャンペーン ID と広告グループ ID を含めることができます。これらは、パフォーマンス最大化キャンペーンとドラフト/実験キャンペーンのキャンペーンレベルおよび広告グループレベルのレポートをサポートします。

```text
AL!{user}!3!{creative}!{matchtype}!{placement}!{network}!{product partition}!{keyword}[!{campaign id}!{ad group id}]
```

* **`creative`**:Google広告クリエイティブ ID。
* **`matchtype`**：キーワード一致タイプ（完全一致の場合は `e`、フレーズの場合は `p`、部分一致の場合は `b`）。
* **`placement`**：広告がクリックされたドメイン。
* **`network`**：クリックが発生したネットワーク（Google検索の場合は `g`、検索パートナーの場合は `s`、表示の場合は `d`）。
* **`product partition`**：製品広告の製品グループ ID。
* **`keyword`**：検索サイトでキーワードをトリガーする、またはコンテンツサイトで最も一致したキーワード。
* **`campaign id`**:Google Ads キャンペーン ID （存在する場合）。
* **`ad group id`**:Google Ads 広告グループ ID （存在する場合）。

動的検索広告の場合、「キーワード」フィールドには自動ターゲットが設定されます。

例：

```text
AL!1234!3!569345525675!e!!g!!adobe express!15557590691!136734402131
```

#### MicrosoftAdvertising

```text
AL!{user}!10!{ad id}!!!!{keyword/order item id}!!{campaign id}!{ad group id}
```

* **`ad id`**:Microsoft Advertising クリエイティブ ID。
* **`keyword/order item id`**:Microsoft Advertisingのキーワード ID。
* **`campaign id`**:Microsoft Advertising キャンペーン ID。
* **`ad group id`**:Microsoft Advertising広告グループ ID。

一部の移行されていないアカウントには、従来のMicrosoft形式が引き続き存在する場合があります。

例：

```text
AL!1234!10!79577297926903!!!!79577437127536!!291647087!1273234845019564
```

#### バイドゥ

```text
AL!{user}!88!{creative}!{placement}!{keyword id}
```

* **`creative`**: Baidu クリエイティブ ID。
* **`placement`**：広告がクリックされた web サイト。
* **`keyword id`**: Baidu キーワード ID。

#### Yahoo! は、日本広告

```text
AL!{user}!94!{creative}!{matchtype}!{network}!{keyword}
```

* **`creative`**: Yahoo! 日本広告クリエイティブ ID。
* **`matchtype`**：キーワード一致のタイプ（完全、`be` 句、大 `bp` い `bb`）。
* **`network`**: クリックが発生したネットワーク（ネイティブ `n` 検索） `s`
* **`keyword`**: トリガーキーワード。

#### ヤンデックス

```text
AL!{user}!90!{ad id}!{source type}!!!{phrase id}
```

* **`ad id`**:Yandex クリエイティブ ID。
* **`source type`** `b`：広告が表示されたサイトのタイプ（検索、`c` コンテキスト/コンテンツ、カテゴリな `ct`）。
* **`phrase id`**:Yandex キーワード ID。

## 分類

[Analytics for Advertising](https://experienceleague.adobe.com/ja/docs/advertising/integrations/analytics/overview) 統合を有効にすると、次の分類が自動的に作成されます。 分類の値は、統合によって自動的に維持されます。

| 分類 | 説明 | DSP | 検索，<br> ソーシャル，&amp;<br>Commerce |
| --- | --- | :---: | :---: |
| **[!UICONTROL アカウント]** | アカウント名。 | &check; | &check; |
| **[!UICONTROL 広告表示 URL]** | 広告に表示される URL。 | | &check; |
| **[!UICONTROL 広告の説明]** | 広告の説明（DSP）または広告本文（検索、ソーシャル、Commerce）。 | &check; | &check; |
| **[!UICONTROL 広告宛先 URL]** | 広告の宛先 URL。 | | &check; |
| **[!UICONTROL 広告グループ]** | 広告グループ名。 | | &check; |
| **[!UICONTROL 広告プラットフォーム]** | 広告DSPまたは検索エンジンの名前。 | &check; | &check; |
| **[!UICONTROL 広告タイトル]** | 広告タイプ（DSP）または広告タイトル（検索、ソーシャル、Commerce）。 | &check; | &check; |
| **[!UICONTROL 広告タイプ]** | 広告タイプ （`text`、`video`、`display`、`native` など）。 | &check; | &check; |
| **[!UICONTROL AdCloud 属性 1]** -<br>**[!UICONTROL AdCloud 属性 5 &#x200B;]** | 今後のカスタム属性用に予約されたプレースホルダー分類。 現在使用中ではありません。 | | |
| **[!UICONTROL Campaign]** | キャンペーン名。 | &check; | &check; |
| **[!UICONTROL Creative エクスペリエンス名]** | 広告インタラクションに関連付けられたクリエイティブエクスペリエンスの名前。テストまたはパーソナライゼーションで使用されるクリエイティブバリエーションのグループを表します。 | &check; | |
| **[!UICONTROL Creative支店名]** | クリエイティブ実験の特定のバリエーションまたはパスを表す、クリエイティブエクスペリエンス内のブランチの名前。 | &check; | |
| **[!UICONTROL Creative ブランチ ID]** | クリエイティブエクスペリエンス内のクリエイティブブランチに割り当てられた一意の ID。 | &check; | |
| **[!UICONTROL Creative名]** | ユーザーに提供された特定の広告クリエイティブアセットの名前。 | &check; | |
| **[!UICONTROL Creative バリアント名]** | クリエイティブエクスペリエンスまたはブランチ内で使用されるクリエイティブの特定のバリアントの名前。 | &check; | |
| **[!UICONTROL キーワード]** | キーワード。 | | &check; |
| **[!UICONTROL キーワード一致タイプ]** | キーワードと一致のタイプ。 | | &check; |
| **[!UICONTROL 踊り場のタイプ]** | ランディングページのエントリがビュースルーかクリックスルーか。 | &check; | &check; |
| **[!UICONTROL 一致の種類]** | 検索一致タイプ。 | | &check; |
| **[!UICONTROL ネットワーク]** | RTB （DSP）または広告ネットワーク名（検索、ソーシャル、Commerce）。 | &check; | &check; |
| **[!UICONTROL 最適化]** | パッケージ名（DSP）またはポートフォリオ名（検索、ソーシャル、Commerce）。 | &check; | &check; |
| **[!UICONTROL プレースメント]** | プレースメント名。 | &check; | |
| **[!UICONTROL 製品ターゲット]** | 商品リスト広告の商品ターゲット。 | | &check; |
